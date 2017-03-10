# Traffic Classifications

## Broadcast Traffic

* **Broadcast Packet** is one that is sent to all ports on a network segment, regardless of whether that port is a hub or switch.
  * there are layer 2 and layer 3 forms of broadcast traffic.
  * e.g. in layer 2, the MAC address FF:FF:FF:FF:FF:FF is reserved broadcast address, and any traffic sent to this address is sent to the entire network segment.
* Layer 3 also has a specific **broadcast address**. — e.g. in a network configured with a 192.168.0/24 the address **192.168.0.255** is the broadcast address \(highest address in segment\)
* The extent to which broadcast packets travel is called the **broadcast domain** - network segment where any computer can directly transmit to another computer without going through a router.

## ![](/assets/traffic-1.png)Multicast Traffic

* Multicast is a means of transmitting a packet from a single source to multiple destinations simultaneously
* Addressing scheme is created that joins packet recipients to a multicast group
* IP addresses in the **224.0.0.0** and **239.255.255.255** range are most likely multicast traffic.

## Unicast Traffic

* **Unicast packet** is transmitted from one computer directly to another.



