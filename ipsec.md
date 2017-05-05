# IPSec

* **Internet Protocol Security \(IPSec\)** - works at the Network layer
* Provides security services for IP traffic.
* IPSec is a family of security protocols.
  * * **Authentication Header \(AH\)** protocol - authentication and integrity services for IP traffic. 
    * **Encapsulating Security Payload \(ESP\)** protocol - encryption services.
    * **Internet Security Association and Key Management Protocol \(ISAKMP\)** - used to negotiate a mutually acceptable level of authentication and encryption methods between two hosts.
      * Acceptable level of security is called **Security Association \(SA\)**
  * **Transport Mode** - header information is not encrypted so that hosts and network devices can read it.
  * **Tunnel Mode** - when IP traffic is encapsulated and sent outside of a LAN, across WAN links to other networks.
    * Since the IP packet is encapsulated in a tunneling protocol \(such as L2TP\), all the info in the packet, including headers + data can be encrypted
* IPSec must be configured on both ends of the connection to use the same encryption algorithms/strengths + key negotiation config.

![](/assets/ipsec-config-1.png)





