# Network Address Translation \(NAT\)

* Network Address Translation \(NAT\) - requires a network device capable of handling public-to-private IP address mappings
* NAT forwards a datagram to the appropriate internal host within a network.
* How it works
  * an organization could have one or two public IP addresses, public IP addresses can be dynamically mapped to internal private IP addresses during the comm. session.
  * static NAT creates a persistent mapping of a public IP address to a private one.
* NAT enables the organization to hide its internal IP address range from external networks and clients.
  * Can prevent attacks on hosts
  * Can prevent IP spoofing of hosts

Network Address Translation \(NAT\)

* * NAT-enabled router has an interface that is part of the home network.
  * A realm with private addresses
    refers to a network whose addresses only have meaning to devices within that network
  * Addresses of 10.0.0.0/24 can only have meaning within a given home network.

## UPnP

* NAT traversal is increasingly provided by **Universal Plug and Play \(UPnP\)**, which is a protocol that allows a host to discover and configure a nearby NAT
* UPnP requires that both the host and the NAT be UPnP compatible.
* UPnP allows external hosts to initiate communication sessions to NATed hosts, using either TCP/UDP.
* Eith UPnP, an application running in a host can request a NAT mapping between its \(private IP, private port \#\) and the \(public IP addr, public port \#\) for some requested public port \#.
* If the NAT accepts the request and create the mapping, then nodes from the outside can initiate TCP connections to \(public IP, public port \#\)



