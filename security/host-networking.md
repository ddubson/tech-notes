# Hardening Host Networking Services

## NetBIOS

\* Network Basic Input/Output System - session layer protocol.

\* Considered an API; developed by Microsoft

\* NetBIOS allows applications to communicate with each other over LANs.

\* Has issues with information leakage - easy to get info about usernames, hosts, shares, and the Windows network by querying NetBIOS, which requires no authentication.

## RDP

\* Remote Desktop Protocol - developed to connect remotely to a host and access it using a GUI.

\* Windows protocol

\* RDP uses both TCP and UDP ports 3389; has 128-bit encryption and uses the RC4 as its encryption protocol

\* Some versions are vulnerable to Man-in-the-Middle attacks, unauthenticated access, information leakage, and pass-the-hash attacks.



