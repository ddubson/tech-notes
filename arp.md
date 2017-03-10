# Address Resolution Protocol \(ARP\)

Because there are both:

* Network-Layer addresses \(IP addresses\)
* Link-Layer addresses \(MAC addresses\)	

There is a need for translation between two addresses schemes:

	**Address Resolution Protocol \(ARP\)** - translates between MAC and IP addresses

![](/assets/arp-1.png)

> Each node has a single IP address, and each node's adapter has a single MAC address. Suppose that the node with IP address 222.222.222.220 wants to send an IP datagram to node 222.222.222.222. Both the source and destination nodes are in the same network \(LAN\). To send a datagram, the source node must give its adapter not only the IP datagram but also the MAC address for destination node 222.222.222.222. The sending node's adapter will then construct a link-layer frame containing the destination node's MAC address and send the frame into the LAN. An ARP module in the sending node takes any IP address on the same LAN as input and returns the corresponding MAC address. Sending node 222.222.222.220 provides its ARP module the IP address 222.222.222.222 and the ARP module returns the corresponding MAC address 49-BD-D2-C7-56-2A

* ARP resolves an IP address to a MAC address.
  * Analogous to DNS \(resolves host names to IP addresses\)
* ARP resolves IP addresses only for nodes on the same subnet

## How ARP works

* Each node \(host or router\) has an ARP table in its memory, which contains mappings of IP addresses to MAC addresses.
* ARP table also contains a time-to-live \(TTL\) value, which indicates when each mapping will be deleted from the table. \(typical expiration is 20mins\)
* The table does not necessarily contain an entry for every node on the subnet; some nodes may have had entries that have expired, whereas other nodes may never have been entered into the table. 
  * Suppose that node 222.222.222.220 wants to send a datagram that is IP-addressed to another node on that subnet
  * The sending node needs to obtain the MAC address of the destination node, given the IP address of that node.
  * If the sending node does not have an ARP entry for the destination host, the sender uses the ARP protocol to resolve the address.
  * The sending node constructs a special packet called an ARP packet.
  * An ARP packet has several fields, including the sending/receiving IP and MAC addresses.
  * Both ARP query and response packets have the same format.
  * The purpose of the ARP query packet is to query all the other nodes on the same subnet to determine the MAC address corresponding to the IP address that is being resolved.
  * Node 222.222.222.220 passes an ARP query packet to the adapter along with an indication that the adapter should send the packet to the MAC broadcast address, namely FF-FF-FF-FF-FF-FF. 
  * The adapter encapsulates the ARP packet in a link-layer frame, uses the broadcast address for the frame's destination address, and transmits the frame into the subnet.
  * The frame containing the ARP query is received by all the other adapters on the subnet, and each adapter passes the ARP packet within the frame up to an ARP module in that node.
  * Each node checks to see if its IP address matches the destination IP address in the ARP packet.
  * The one node with a match sends back to the querying node a response ARP packet with the desired mapping.
  * The querying node can then update its ARP table and send its IP datagram, encapsulated in a link-layer frame whose destination MAC is that of the node responding to the earlier ARP query.

* The query ARP message is sent within a broadcast frame, whereas the response ARP message is sent within a standard frame.
* ARP is a plug-and-play - a node's ARP table gets built automatically - it doesn't have to be configured by a system's administrator.
* If a node becomes disconnected from the subnet, its entry is eventually deleted from the tables of the nodes remaining in the subnet.
* ARP is best considered a protocol that straddles the boundary between the link and network layers - not fitting neatly into the simple layered protocol stack.

## Sending a Datagram to a Node off the Subnet

![](/assets/arp-2.png)

 There are two types of nodes: **hosts** and **routers**

* Each host has exactly one IP address and one adapter
* A router has an IP address for each of its interfaces.
* For each router interface there is also an ARP module \(in the router\), and an adapter.
* Because the router in 5.19 has two interfaces, it has two IP addresses, two ARP modules, and two adapters.
* Each adapter in the network has its own MAC address.
  * Suppose that host 111.111.111.111 wants to send an IP datagram to a host 222.222.222.222
  * The sending host passes the datagram to its adapter
  * The sending host must also indicate to its adapter an appropriate destination MAC address
  * In order for a datagram to go from 111.111.111.111 to a node on Subnet 2, the datagram must first be sent to the router interface 111.111.111.110 which is the IP address of the first-hop router on the path to the final destination.
  * The appropriate MAC address for the frame is the address of the adapter for router interface 111.111.111.110, E6-E9-00-17-BB-4B.
    * How does the sending host acquire the MAC address for 111.111.111.110? By using ARP.
  * Once the sending adapter has theis MAC address, it creates a frame \(containing 222.222.222.220\) and send the frame into Subnet 1
  * The router adapter on Subnet 1 sees that the link-layer frame is addressed to it, and therefore passes the frame to the network layer of the router.
  * The router determines the correct interface on which the datagram is to be forwarded by using the forwarding table.
  * The interface then passes the datagram to its adapter, which encapsulates the datagram in a new frame and sends the frame into Subnet 2.
  * The destination MAC address of the frame is indeed the MAC address of the ultimate destination and how does the router obtain this destination MAC address? From ARP!



