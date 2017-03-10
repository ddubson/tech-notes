# ICMP

* **ICMP - internet control message protocol**
* Purpose to debug information on the network
* ICMP is encapsulated in IP - no layer 4 protocol \(transport\)
* Several different types of ICMP, each trying to provide about a network condition \(only handful used regularly\)
* Structure: ICMP Header, Data Area

## Types

* **ICMP 1 - Proof of Life\***
  * icmp echo request and response
  * generated using ping program
  * type 8 - sends the alphabet back and forth
  * sender: echo request, receiver: echo response
* **ICMP 2 - Leave me alone\***
  * Host has a datagram for another network it sends the datagram to the router
  * If the router determines that another router should be used
    * sends redirect message \(type 5\) to the sender
    * It also forwards the datagram, but hopefully only once.
  * Type 5 - Redirect
* **ICMP 3 - You ran out of time\***
  * Routing loops are allowed
  * Each datagram includes a TTL field - decremented by each router through which the datagram passes.
  * If it reaches 0, sends a TTL exceeded \(Type 11\) ICMP message to the sender
  * Includes the original message
* **ICMP 4 - Can’t get there from here\***
  * IP address of a non-existent or down machine
  * If a router determines it cannot deliver the datagram,
    * sends a Destination unreachable \(Type 3\) datagram to the sender
    * several cases: router is offline, entire network is offline, router doesn’t know.

ICMPv6 - RFC 4443



