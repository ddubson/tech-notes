# Ethernet Frame

## Ethernet Frame Structure

* Let's consider sending an IP datagram from one host to another host, with both hosts on the same Ethernet LAN
* Let:
  * the sending adapter, adapter A, have the MAC address AA-AA-AA-AA-AA-AA
  * the receiving adapter, adapter B, have the MAC address BB-BB-BB-BB-BB-BB.	
* The sending adapter encapsulates the IP datagram within an Ethernet frame and passes the frame to the physical layer
* The receiving adapter receives the frame from the physical layer, extracts the IP datagram, and passes the IP datagram to the network layer.

![](/assets/eth-1.png)

* Data field \(46 - 1,500bytes\) - carries the IP datagram.
  * Maximum Transmission Unit \(MTU\) is 1,500 bytes, IP is fragmented otherwise.
  * Minimum size of the data field is 46 bytes, otherwise it is padded to 46
* Destination Address \(6 bytes\) - contains the MAC address of the destination adapter. When adapter receives the Ethernet frame whose destination address or broadcast address, it passes the contents of the frame’s data field to the network layer. Otherwise it discards the frame.
* Source Address \(6 bytes\)\* - field contains the MAC address of the adapter that transmits the frame onto the LAN.
* Type field \(2 bytes\)\* - field permits Ethernet to multiplex network-layer protocols.
* Cyclic Redundancy Check \(CRC\) \(4 bytes\)\* - allows the receiving adapter to detect bit errors in the frame.
* Preamble \(8 bytes\)\* - the frame beings with a preamble
  * First 7 bytes allows the receiving adapters to “wake up” and sync their clocks to that of the sender’s clock.
  * Adapters might be out of sync, adapters don’t always transmit at the same rate \(drift\)
  * Receiving adapter can lock onto source adapter’s clock by locking onto the bits in the first 7 bytes.
  * 2 bits of the eighth byte of the preamble alert receiving adapter that “important stuff” is about to come.



* Ethernet uses baseband transmission - adapter sends a digital signal directly into the broadcast channel.
* The interface card \(NIC\) does not shift the signal into another frequency band, as is done in ADSL and cable modems.



* Many Ethernet technologies use Manchester Encoding.
* With Manchester encoding, each bit contains a transition:
  * A 1 has a transition from up to down
  * 0 has a transition from down to up.

![](/assets/eth-2.png)

* The reason for Manchester encoding is that the clocks in the sending and receiving adapters are not perfectly synchronized.
* By including a transition in the middle of each bit, the receiving host can synchronize its clock to that of the sending host.
* Once the receiving adapter's clock is synchronized, the receiver can delineate each bit and determine whether it is a 1 or 0.
* Manchester encoding is a physical layer operation rather than a link layer operation.

## Unreliable Connectionless Service

* All of the Ethernet technologies provide connectionless service to the network layer.
  * When adapter A wants to send a datagram to adapter B, adapter A encapsulates the datagram in an Ethernet frame and sends the frame into the LAN, without first handshaking with adapter B.
* Ethernet tech provide an unreliable service to the network layer.
  * When adapter B receives a frame from adapter Am it runs the frame through a CRC check, but neither sends an acknowledgment when a frame passes the CRC check nor sends a negative acknowledgement  when a frame fails the CRC check.
  * When a frame fails the CRC check, adapter B simply discards the frame. Adapter A has no idea whether its transmitted frame reached adapter B and passed the CRC check.
  * This lack of reliable transport helps to make Ethernet simple and cheap.
* If there are gaps due to discarded Ethernet frames, then it depends on type of transport layer TCP or UDP protocol used.
  * If app is using UDP, then the app in Host B will indeed see gaps in the data.
  * If the app is using TCP, then TCP in host B will not acknowledge the data contained in discarded frames, causing TCP in host A to retransmit.



