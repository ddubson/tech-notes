# Internet Protocol \(IP\)

Internet Protocol \(IP\) datagram has a total of

* 20 bytes of header
  * If the datagram carries a TCP segment, then each datagram carries a total of 40 bytes of header \(20 bytes IP + 20 bytes TCP\) along with the app layer message.

IP Datagram Fragmentation

* Maximum Transmission Unit \(MTU\) - maximum amount of data that a link layer frame can carry
  * the MTU of the link-layer protocol places a hard limit on the length of an IP datagram.
* The solution is to split IP datagrams into smaller fragments and encapsulate each of the smaller IP dgrams in their own frame, and send them to the outgoing link.
* Each link along the path can have different protocols, thus supporting different size MTUs.

* Each of the smaller datagrams is referred to as **fragment**
  * Fragments need to be reassembled before they reach the transport layer at the destination
  * The designers of IPv4 put the job of datagram reassembly in the end systems rather than in network routers.



* When a destination host receives a series of datagrams from the same source, it needs to determine whether any of these dgrams are fragments of some original, larger datagram.
* If some dgrams are fragments, it must determine when it has received the last fragment and how the fragments it has received should be pieced back together to form the original datagram.



* To allow the destination host to perform the reassembly, IPv4 was designed with identification, flag, and fragmentation offset fields in the IP datagram header.

* When a dgram is created, the sending host stamps the datagram with an identificaition \# as well as src/dest addresses.
* The sending host increments the ID \# for each dgram it sends.
* Each fragment of the original dgram is stamped with SRC/DEST address and the ID\# of original dgram



* Because IP is unreliable, some fragments may never arrive, for this reason the last fragment of a dgram has to have the
  flag bit
  set to 0, where all the preceding dgram fragments have it set to 1.
* * The offset field determines where the fragment fits within the original dgram.

Example:

* a datagram of 4,000 bytes \(20 bytes of IP header + 3980 bytes of IP payload\) arrives at a router and must be forwarded to a link with an MTU of 1,500 bytes.
* 3,980 data bytes in the OG dgram must be allocated to 3 separate fragments
* Suppose the OG dgram is stemped with ID \# of 777.

![](/assets/ip-1.png)

At the destination, the payload of the dgram is passed to the transport layer only after the IP layer has fully constructed the original IP datagram.

* If one or more of the fragments does not arrive at the destination, the incomplete datagram is discarded and not passed to the transport layer.
* If TCP is being used at the transport layer, then TCP will recover from this loss by having a retransmit.

Fragmentation Shortcomings

* complicates routers and end systems which need to be designed to accommodate dgram fragmentation and reassembly.
* Fragmentation can be used to create lethal DoS attacks, whereby the attacker sends bizarre series of unexpected fragments.



