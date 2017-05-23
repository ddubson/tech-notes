# nmap - network scanning and analysis tool

## Useful commands

```bash
# default scan
nmap [hostname|IP]

# service scan
nmap -sV [hostname|ip]

# banner check
nmap -A [hostname|ip]

# service scan with output logging
nmap -sV -oA log.txt [host|ip|subnet]

# service scan with output logging.
nmap -sV -oA log.txt localhost

# e.g. Identify all network devices with port 80 open
nmap -oA log.txt -p 80 192.168.1.0/24 && clear && cat log.txt.gnmap | grep "open"
/*
    Output:
        * .xml
        * .nmap - human readable
        * .gnmap - greppable | easily searchable output
*/

# specific port scan
nmap –p1-1024 [host|ip|subnet]
nmap –p 80 [host|ip|subnet]

# Scan all 65,535 available ports of a given machine
nmap -p- localhost

# Scan a list of targets located in an external file
nmap -iL targets.txt

# Scan a target and show reason for its service discovery
nmap --reason -sV localhost

# Perform ping sweep on a local class C subnet to determine which hosts are up (or at least ACK ICMP)
nmap -sn 192.168.1.0/24

# Scan all hosts' top ports without an initial ping sweep 
nmap -Pn -p1-1024 192.168.1.0/24

# Scan range of hosts to get their DNS PTR entries (example IP address below, do not use as is) - zero-packet recon
nmap 74.125.224.32-41 -sL

# Scan using TCP SYN, pinging a specific port with a TCP SYN packet and seeing if that port responds
nmap -PS 80 localhost

# TCP Connect Scan
nmap -sT localhost

# SYN Stealth Scan
nmap -sS localhost

# FIN Scan
nmap -sF localhost

# XMas Tree Scan - flags FIN, URG, and PUSH flags on a packet header
nmap -sX localhost

# Null scan - no flags on the packet header
nmap -sN localhost

# Scan with operating system discovery mode
nmap -O localhost

# Verbosity flags
# -v, -vv, -vvv
nmap -v -sV localhost

# Scan with packet tracing
nmap --packet-trace 192.168.1.1
```



