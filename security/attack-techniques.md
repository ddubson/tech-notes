# Attack Techniques

## Network Attacks

### SYN Flood

`SYN` flood form of DDOS in which an attacker sends a succession of[`SYN`](https://en.wikipedia.org/wiki/SYN_%28TCP%29)requests to a target's system in an attempt to consume enough server resources to make the system unresponsive to legitimate traffic

In normal operation, a TCP connection uses a three-way handshake to establish a TCP session for communication. The initial SYN packet is sent to destination, and an awaits a `SYN-ACK` packet in response.

![](/assets/syn-flood-1.png)

In a SYN flood, the sender does not reply with an ACK in reply to SYN-ACK. 

The malicious sender can either:

1. Actively not respond with a `ACK` packet.
2. Spoof a fake IP address in packet payload, so that victim host sends a `SYN-ACK` reply to an unsuspecting or an unreachable spoofed address.

Victim server will wait for X amount of time for an ACK reply -- since network congestion might be a factor in ACK delay.

In this attack, half-open connections \(pending for ACK\) are using up server resources.

Eventually, the number of open pending connections can overwhelm the server and it will no longer be able to accept connections.

