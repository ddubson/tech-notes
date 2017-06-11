# Packet Analysis

Encapsulation process creates a \*protocol data unit \(PDU\)\* which includes all the data being sent and all header or footer information added to it.

PDU in its final form reaches the physical layers and then sent to the destination host.

## Tapping into the wire

\* Need a NIC that supports \*Promiscuous Mode\*

\* In promiscuous mode, NIC passes every packet it sees to the host’s processor, regardless of addressing.

\* Wireshark promiscuous mode has to be enabled to capture traffic from all network devices.

\* Hubs offer full visibility into the network for packet sniffers since hubs are based on broadcast traffic that the sniffer can ingest.



### Sniffing in a Switched Environment

\* Hard to do since switches send packets to specific addresses, can only read broadcast traffic and traffic sent to own machine.

\* There are 4 ways to capture traffic from a target device on a switched network:

	\* Port Mirroring

	\* Hubbing Out

	\* Using a Tap

### 	\* ARP Cache Poisoning![](/assets/packet-1.png)Port Mirroring

\* \#networking/technique/port mirroring\# or port spanning - easiest way to capture traffic on a switched environment

\* Must have access to command line mgmt interface on the switch

\* The switch must support port mirroring and an empty port into which you can plug your sniffer.

\* Issue command that forces the switch to copy all traffic on one port to another port.

![](/assets/packet-2.png)

### Hubbing Out

\* Technique by which you segment the target device and your analyzer system on the same network segment by plugging them directly into a hub.

\* Must have physical access to the switch

![](/assets/packet-3.png)

\#\#\# Using a Tap

\* A network tap is a hardware device that you can place between two points on your cabling system in order to capture the packets between two points.

\* Two primary network taps:

	\* Aggregated - has three ports.

	\* Non-Aggregated - has four ports

\* Both sit in between the devices.

\* Taps typically require power supply



\#\#\#\# Aggregated Taps

\* Only one physical monitor port for sniffing bidirectional traffic

![](/assets/packet-4.png)

\#\#\#\# NonAggregated Taps

\* Has two monitor ports: one is used for sniffing traffic in one direction and the other port is used for sniffing traffic in the other 

direction.

![](/assets/packet-5.png)

 ARP Cache Poisoning

\* \*ARP Spoofing\* process of sending ARP messages to an Ethernet switch or router with fake MAC \(layer 2\) addresses in order to intercept the traffic of another computer.

![](/assets/packet-6.png)

\* \*Cain & Abel\* tool for Windows can help with ARP poisoning.

