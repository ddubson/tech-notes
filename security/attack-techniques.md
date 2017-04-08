# Attack Techniques

## Network Attacks

### SYN Flood

`SYN` flood form of DDOS in which an attacker sends a succession of[`SYN`](https://en.wikipedia.org/wiki/SYN_%28TCP%29)requests to a target's system in an attempt to consume enough server resources to make the system unresponsive to legitimate traffic

In normal operation, a TCP connection uses a three-way handshake to establish a TCP session for communication. The initial SYN packet is sent to destination, and an awaits a `SYN-ACK` packet in response.

![](/assets/syn-flood-1.png)

In a SYN flood,

```
* Attacker sends X number of SYN packets
* Victim sends a SYN-ACK in response to SYN packets
* Attacker can send the packets with a spoofed return IP address or not respond to SYN-ACK at all.
* Victim server will wait for X amount of time for an ACK reply -- since network congestion might be a factor in 
ACK delay.
* In this attack, half-open connections (pending for ACK) are using up server resources.
* Eventually, the number of open pending connections can overwhelm the server and it will no longer be able to 
accept connections.
```

#### Mitigations and Countermeasures

[RFC 4987](https://tools.ietf.org/html/rfc4987)

[Cisco - Defenses against TCP SYN Flooding attacks.](http://www.cisco.com/c/en/us/about/press/internet-protocol-journal/back-issues/table-contents-34/syn-flooding-attacks.html)

