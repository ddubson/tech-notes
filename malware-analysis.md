# Dynamic Host Configuration Protocol \(DHCP\)

Obtaining a Host Address: DHCP

* Host addresses within an organization are configured by DHCP
* Dynamic Host Configuration Protocol \(DHCP\)
  * allows a host to obtain an IP addr. Automatically.
* A host can obtain the same address every time it is connected, or be assigned a temporary address that will be different each time.
* DHCP also allows a host to learn additional information, such as its subnet mask, the address of its first-hop router \(default gateway\), and the address of its local DNS server.
* DHCP is often referred to as a plug-and-play protocol
* DHCP is composed of a **4 step process** for a newly arriving host:
  * **DHCP Server Discovery**
    * done using a DHCP discover message which a client sends within a UDP packet to port 67. DHCP client creates an IP dgram containing its DHCP discovery message along with a broadcast IP addr of 255x4, and this host source address as 0.0.0.0. The DHCP client passes the IP dgram to the link layer, which then broadcasts this frame to all nodes attached to the subnet.
  * **DHCP Server offer\(s\)**
    * a receiving server responds to client with a DHCP offer message that is broadcast to all nodes on the subnet. Each server offer message contains the transaction ID of the received discover message, the proposed IP address for the client, the network mask, and an IP address lease time--the amount of time for which the IP address is valid.
  * **DHCP request**
    * newly arriving client will choose from among one or more serer offers and respond to its selected offer with a DHCP request message, echoing back the configuration parameters.
  * **DHCP ACK**
    * server responds to the DHCP request message with a DHCP ACK message, confirming the requested parameters.



