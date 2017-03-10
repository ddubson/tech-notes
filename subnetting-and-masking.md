# Subnetting and Masking

* Networks grow and messaging on the network grows as well, slowing down as it grows.
* Rule of thumb for size of network
  * about 100 nodes per subnet
  * about 30 nodes for very intense applications
* Classes A, B, and C are for user networks

![](/assets/subnet-1.png)

* Each class has a default value
* The network mask \(subnet mask\)
  * where there are 1s indicates the network ID
  * where the 0s are the host ID
* Masks
  * A: 255.0.0.0
  * B: 255.255.0.0
  * C: 255.255.255.0
* Netmask has two parts
  * network specific
  * host specific
* Defined by Address Class type
* Subdivide the network into subnetworks
  * each with fewer hosts
* **Subnet** - LAN connected to other LANs via some internet working device \(e.g. router\)
  * Broadcasts are restricted to a subnet
  * All hosts on a subnet \(LAN\) can communicate with MAC addresses
  * Network layer \(IP\) addresses are required to communicate with hosts on other subnets \(LANs\)
* Subnet scheme:
  * Network specific address
  * Sub-network address
  * Host address
* Extend the 1s into the host ID portion - borrowing from the host ID to give us more smaller networks.![](/assets/subnet-2.png)
* Each subnet is a network, must have a router to get out
  * Directed broadcast
  * Limited broadcast
  * Network id
  * Range of usable host addresses
* Supernetting/Aggregation
  * Used to connect multiple small addresses to larger address space
  * Steal bits from the network id portion
* Break up 192.168.1.0 network into 4 groups
  * 1st subnet will be 0-63 -&gt; masked by 255.255.255.0
  * 2nd subnet will be 64-127 -&gt; masked by 255.255.255.64
  * 3rd subnet will be 128-191 -&gt; masked by 255.255.255.128
  * 4th subnet will be 192-255 -&gt; masked by 255.255.255.192



