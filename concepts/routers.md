# Routers and Routing

**Forwarding Function -** actual transfer of packets from a router's incoming links to the appropriate outgoing links

![](/assets/routers-2.png)

Four components of a router are:

* **Input Ports **- performs the physical layer functions of terminating an incoming physical link to a router;
  * data link layer function needed to interoperate with the data link layer function at the remote side of the incoming link
  * performs a lookup and forwarding function so that a packet forwarded into the switching fabric of the router emerges at the appropriate output port.
  * Control packets are forwarded from an input port to the routing processor.
* **Switching Fabric - **connects the router's input ports to its output ports
  * completely contained within the router--a network inside of a network router
* **Output Links **- stores the packets that have been forwarded to it through the switching fabric and then transmits the packets on the outgoing link.
  * performs the reverse data link layer and physical layer functionality of the input port.
* **Routing Processor **- executes the routing protocols, maintains the routing information and forwarding tables, and performs network management functions within the router.



