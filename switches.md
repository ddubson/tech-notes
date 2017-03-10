# Layer 2 Switch

**Switches** - best alternatives to hubs in a prod or high density network; designed to repeat packets, but only sends data to computer for which the data is intended.

* must be able to uniquely identify devices based on their MAC addresses.
* _full duplex mode_ - able to send and receive packets simultaneously between ports
* switches store the Layer 2 address \(MAC\) of every connected device in a **CAM** table.
* When a packet is transmitted, the switch reads the header info and compares the info to that which is stored in the CAM table.
* TTL of CAM table entries is roughly 300 secs, old entries are flushed
* Switches send data to specific ports, reducing traffic
* If a switch does not know where the destination MAC address is \(not in CAM table\), the switch floods the ports asking who has the MAC address \(except the source port\)

![](/assets/switches-1.png)

![](/assets/switches-2.png)

Switches must be able to uniquely identify devices based on their MAC addresses, which means they must operate on the data link \(layer II\) layer of the OSI

* Switches store layer 2 address of every connected device in a \*CAM table\* - which acts a traffic cop.
* When a packet is transmitted, switch reads layer 2 headers in packet, and determine which port to send the packet.



