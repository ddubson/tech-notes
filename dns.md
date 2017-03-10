# Domain Name System \(DNS\)

## Brief History

* In beginning, HOSTS.txt
* single monolithic file mapped names of all ARPANETs hosts to their addresses
* Maintained by single organization \(SRI\)
* Problems
  * Consistency/latency
  * Traffic and load on SRI-NIC
  * Collisions
  * Searching the file was linear \(O\(n\)\)
* Goals for design of DNS \(Domain Name System\)
  * Local admin with global availability
  * Hierarchical namespace

![](/assets/dns-1.png)

# Domain Name System

* **Naming service** - responsible mapping domain names to IP addresses
  * In email addr.
  * In URLs
  * ...into IP addresses and other data
* A distributed database
  * partitioned into zones
  * managed in a distributed, decentralized way
  * available globally across Internet
* The Domain namespace
  * DBs have indexes
  * DNS is no diff
  * DNSs indexes are those funny dotted names which are properly called domain names
  * Domain names are actually paths in an inverted tree
* An inverted tree is made up of nodes and links between nodes
* Each node is connected to its parent by a single link
* One node can be parent to arbitrary number of children
* Each node has a label between, 0 and 63 bytes in length
* The root node at the top has a special reserved label written as "" \(zero-length label\)
* A label isn't sufficient to uniquely identify a node in the tree

You need the node's domain name: the series of labels from the node to the root, read with dots separating the labels.

## Domains

* Domains are groups of related nodes - subtree of the namespace
* Domains are identified by a domain name - the domain name of the node at the apex of the subtree

![](/assets/dns-3.png)

* Subdomains are domains contained within another domain
  * the apex of the subdomain is within the parent domain
  * the subdomain ends in the name of its parent, e.g. hp.com ends in com
* An organization manages a domain
  * ICANN controls the root domain
  * Verisign controls the com domain
* Delegation allows an organization to assign control of a subdomain to another organization
* The parent now contains pointers to the source of data in the subdomain
* The parent and child are now separate administrative containers, separate zones

![](/assets/dns-5.png)

* TLD – Top Level Domain \(com, gov, mil, net, etc.\)
* CcTLD – country code TLD \(.il, it, .co.uk, etc.\)

## Name Servers

* DNS is a client-server system
* The servers are called name servers or \(DNS Servers\)
* The clients are called resolvers, and they query name servers
* Resolver query name servers
* Name servers load data in zones, the admin units in DNS
  * Name servers may load thousands of zones, but no name server holds the entire namespace
  * A name server that loads the entire zone is authoritative for that zone.
* Name servers answer queries from resolvers
* But also queries from other name servers

## Resolvers

* Often part of the device's OS: Windows, Mac OSX, or iOS
* Take data from application and create DNS queries
* The resolver queries a range of DNS servers and wait for response
* When response is received, it unmarshals the data and sends back to app
* Resolvers abstract the link between app and the DNS

## Name Resolution

* Resolution takes a top-down approach by default
* From the root name servers, if no better match is found
* The roots can refer to any querier to the name servers authoritative for the proper to-level zone.
* The querier than queries the name server for that top level zone, which refer it to the name servers for the proper second-level zone.
* Eventually the querier reaches a name server authoritative for the zone that contains the domain name it's interested in
* That name server answers the query.
* Queries are either: recursive or iterative
* Accepting a recursive query obliges a names server to do all the work necessary to find an answer
  * Which may include following several referrals
  * The name server may not send a referral in response
* A name server responds to a non-recursive query with the best answer it already knows, often a referral

## DNS Messages

* Queries and responses are types of DNS messages
  * Usually transferred over UDP
* Sharing a common format:

![](/assets/dns-6.png)

* Header
  * OPCODE = QUERY
  * qr bit - query/response 0/1
  * rd bit - recursion desired or iterative 1/0
* Question
  * Domain Name: the domain name the querier is interested in
  * Class: almost always IN for InterNet
  * Type: the type of data \(record\) the querier is interested in
* Answer/Authority/Additional
  * Carry resource records \(RRs\)
  * Answer the query
  * Or refer to other name servers

## Caching

* The names and addresses of the com name servers
* The names and addresses of the infoblox.com name servers
* The addresses of www.infoblox.com
* Each resource has a TTL which governs how long the cached record stays in the name server
  * TTLs range from seconds to days
  * The admin of the zone that contains the record decides the TTL

## Server selection and retransmission

* most zones have 1+ name servers
  * recursive name servers need to choose which ones to query
* Queries/responses sent over UDP
  * so they can get lost
  * both resolvers and name server must handle retransmissions
* Name server selection is based on implementation
* BIND name servers use RTT \(round-trip time\) to choose
  * time how long a response takes
  * they favor the quickest name server 
* Retransmission algos also depend on implementation
  * All name servers send queries and await responses
  * If they don’t receive a response within timeout, they retransmit the query - to another name server if possible.

## Authoritative / Recursive / Caching Name Servers types

* Authoritative NS - auth for one or more zones
  * main function is to answer non-recursive queries for data in its authoritative zones
  * meaningful when a specific context is specified
* Recursive NS - willing to handle recursive queries
  * also cache responses
  * sometimes called caching name servers
  * if they aren't authoritative, they are caching-only name servers    

## Primary and Secondaries

* Primary NS - read zone data file
* Secondary NS - transfers data from primary NS via AXFR Query
* Serial Numbers and REFRESH
  * A zone's SN is an indic. of version of the data in that zone
  * Secondary checks primary to see if the serial \# is higher on the primary, zone transfer is requested if serial \# is higher on primary.
* Primary and secondary system exists primarily to make it easy to set up several authoritative name servers for a zone and manage the zone data from one place.

## Recursive Resolution

* Forwarding
  * A recursive NS with a forwarder doesn't query the roots and follow referrals
  * Instead, it forwards the recursive query to another NS, its forwarder
  * The forwarder assumes the responsibility for resolving the query
  * The forwarder replies to the first name server, which relays the answer to the resolver.
  * forwarder is the NS that receives the forwarded query
  * originally, to build a rich cache on a central name

## Makes and Models: BIND, Windows DNS Server

* BIND - Berkley Internet Name Domain. Open Source, 1984, current version 9.10
* Windows DNS Server: formerly MS DNS Server, part of Windows Server OS. released in 1996, part NT 4.0

## Resource Records

* Units of data stored in the DNS namespace
* In a DNS message, they have a binary format
* In a zone data file, textual format \(presentation format or master file format\):

```
owner-name    [TTL]    [class]    type    RDATA
```

e.g.

```
www            3600    IN    A    50.19.85.84
infoblox.com.    1h        IN      MX    10      mx1.infoblox.com
```

* TTL - how long to cache the record
* Class - almost always IN \(InterNet\)
* Type - SOA, A, AAAA, MX, etc.
* RDATA - depends on type, 
  * A record - dotted octet
  * MX record - 16bit pref value+domain name
* Resource Record Set \(RRSet\) that share the same domain name, class, and type
* All of the A records for www.infoblox.com share the same RRset

### ’A’ Record - IPv4 Address

Presentation format:

`owner-name    [TTL]    IN    A    <32-bit IPv4 Address>`

e.g.

`www    IN    A    50.19.85.84`

### ‘AAAA’ Record - IPv6 Address

Presentation Format:

`owner-name        [TTL]    IN    AAAA    <128-bit IPv6 Address>`

e.g.

`www    3600    IN    AAAA    2406::da00::ff00::3213::5554`

* If a domain name has both A and AAAA records attached, the one used depends on the clients
  * Some clients prefer IPv6 over IPv4, others the reverse
  * Some clients will look up both and try to connect over both if available
    * Using the one that connects first
* The Algorithm is known as Happy Eyeballs

### ‘PTR’ Record - Pointer

* Chiefly used for reverse mapping
  * Mapping from an IP address to a Domain name
  * A and AAAA records are only useful for forward mapping
* Two special domains in the namespace handle reverse mapping
  * In-addr.arpa for IPv4
    * Labels of a domain name of IPv4 addr in reverse addr
  * Ip6.arpa for IPv6
* Labels are the hex digits of an IPv6 addr in reverse order

![](/assets/dns-7.png)

* Reverse order is necessary to make delegation sensible.
* Presentation Format

	`owner-name		[TTL]	IN	PTR		<domain-name>`

###  ‘CNAME’ Record - Alias

* Presentation format:

`owner-name		[TTL]	IN	CNAME	<domain-name>`

e.g.

`alias		3600	IN	CNAME	official.infoblox.com`

* CNAME records are singletons - no other records can be attached if one exists.
* Queries for a record type other than CNAME wouldn’t match the CNAME
* So authoritative name servers also check whether the domain name in the query is an alias by looking for CNAME records.
* Recursive name servers that receive CNAME records as a response restart the query
  * Replacing the alias with the c name
* So don’t' CNAME records

### ‘MX’ Record - Mail Server

* Presentation format:

`owner-name		[TTL]	IN 		MX		<16-bit preference>	<mail exchanger>`

e.g.

`@		IN	MX	10 mx1.infoblox.com`

* MX records list the mail exchangers for an email destination

### ’SRV’ Record - Service

* Presentation format:

`owner-name		[TTL]	IN	SRV		<16-bit priority>	<16-bit weight>		<port>	<target>`

e.g. 

```
_http._tcp.www		IN	SRV		0	0	80	www1
_http._tcp.www		IN	SRV		0	0	80	www2
```

### ‘TXT’ Record

* Used to attach some text to a DNS entry
* Allows to associate free format text with a domain name
* Presentation format:

`owner-name		[TTL]	IN	TXT		“string” [“string” …]`

e.g.

`@	IN	TXT		“infoblox.com.	IN	TXT “v=spf1 mx a”`

### ‘SOA’ Record - Start of Authority \(Infrastructure\)

* Presentation format:

`owner-name		[TTL]	IN SOA	<mname>	<rname> <32-bit serial number>`

e.g.

`IN		SOA		ns1.infoblox.com.	dns.infoblox.com.	(2015060600, 1h, 15m, 30d, 10m)`

### ’NS’ Record - Namespace \(Infrastructure\)

* Presentation format:

`owner-name		[TTL]	IN	NS	<name-server>`

e.g.

```
@		IN	NS	ns1.infoblox.com.
		IN	NS	ns2.infoblox.com.
		IN	NS	ns3.infoblox.com.
		IN	NS	ns4.infoblox.com.
```

## Dynamic Update

* OG modifying zone data required editing a zone data file and reloading a zone
  * required admin intervention or stream editing
* \#rfcs/2136\# - published in 1997, codified a mechanism to do this, called dynamic update
* Dynamic updates are carried in DNS messages
  * OPCODE = UPDATE
  * Sections are redefined:
    * Zone
    * Prerequisite
    * Update
  * Prerequisites are optional conditions which if included must be true for the subsequent update to be processed
  * 5 types:
    * RRset exists \(value indp\), e.g. www.infoblox.com has a A record
    * RRset exists \(value dep\), e.g. www.infoblox.com has the A record 10.0.0.1
    * RRset does not exists, e.g. www.infoblox.com has no A record
    * Name is in use, e.g. www.infoblox.com owns at least one record
    * Name is not in use, e.g. www.infoblox.com doesn't own any records
  * 4 types of update
    * Add RRs to an RRset
    * Delete and RRset, e.g. delete all of www.infoblox.com's A records
    * Delete all RRsets from a name, e.g. delete all records from www.infoblox.com

Delete an RR from an RRset, e.g. delete www.infoblox.com's A record pointing to 10.0.0.1



