# Host Threats

## Malware

* Term evolved from /malicious software/ 
* Classified in several ways, depending upon characteristics that include:
  * Method of propagation
  * What the malware does
  * What it targets on the system
  * etc.

### Virus

* virus is a type of malware
* Must be propagated through a definite user action — cannot spread itself.
* Usually propagated via download, removable storage media, transmission of infected files from system to system.
* Have a variety of effects on systems
  * slowing down the system
  * filling up the storage space
  * slowing down the host’s network
  * recording passwords
  * rendering host unusable or unbootable
* TeraBit Virus Maker is an app that can build a virus

### Worm

* worm Similar to virus; but able to self-replicate and spread to other logical sections  or networks.
* Examples of famous worms: MyDoom, Blaster, Win32Conficker

## Trojan

* trojan Specialized piece of malware
* Software that seems to be of value to the user - game, utility, or other
* Usually has the goal of collecting personal information from a user
* Can also be used as a generic container used to spread viruses and worms.

### Adware

* adware Malicious ads — pop-ups.
* Can disguise software with malicious intent
* Adware can sometimes carry malware \(trojans or viruses\)
* User may get adware by clicking on a web link or download something that changes browser settings on the host, resulting in a stream of pop-up

### Spyware

* spyware malware with a specific purpose.
* Can be a virus or trojan 
* Tend to classify spyware by its /function/ rather than type
* Used for observing user’s actions and recording them, as well as stealing sensitive data \(passwords, CC info\)
* Has the ability to send data back to the attacker so that user cant easily detect it.

### Rootkits

* rootkit malware that attempts to infect critical operating system files on the host.
* AV software cannot easily detect rootkits so they can reside on the system for a while before detection.
* Can thwart AV software by sending false information to its collectors.

### Backdoors

* backdoor - entry method into a piece of software \(app or OS\) that wasn't intended to be used by normal users.
* Most are created as a maintenance entry point during software development, usually by programmers creating the software.
* Should beclouded prior to software release, but often forgotten about.
* Can also be created by hackers during an intrusion into the system.
* Vulnerability testing can often detect these points of entry.

### Logic Bomb

* logic bomb - often a script set to execute at a particular time or under certain circumstances - designed to take malicious action when it executes. 
* Usually the result of a malicious insider or a disgruntled administrator

### Botnets

* botnet - distributed type of malware attack that uses a remotely controlled piece of software that has infected several different computers.
* Intention is to create large robot network for large scale targeted attacks.
* The infected hosts are called \*bots\* or \*zombies\* since they only obey the attacker’s commands.
* Most are used for \#security/DDOS attacks - /Distributed Denial of Service/ attacks.

### Ransomware

* ransomware - a user downloads malware or an attacker gets to a host - when malware executes, it can encrypt user files or lock the user out of the system, holding the system ransom.
* Another variant of the attack is called /scareware/ - message states that the user has been caught doing something illegal, the user must pay a fine to keep it hush hush.

![](/assets/host-threat-1.png)

## Polymorphic Malware

* Type of malware that is able to change itself every time it infects a new host - usually to avoid AV software detection.

* Similar to /metamoprhic malware/ changes itself upon different generations and versions, rather than upon each infection from host to host.

### Armored Virus

* Like other types of viruses - but use advanced techniques to avoid detection/analysis
* It can change its tactics, characteristics, use of encryption for avoidance of signatures.
* Usually larger in size than regular viruses.

## Host Attacks

### Spam

* spam -large volume of email that is sent to a recipient.
* Most spam is harmless except a large variety of phishing attacks that can come in the form of spam.

### Phishing

* phishing - social engineering attack usually communicated through email.
* Attacker tries to get a user to click on a malicious link in the email, usually via a false story or context.

### Spim

* A play on two terms: spam and instant messaging \(IM\) - a new form of spam that occurs over chat and IM services.
* Can be used for phishing attacks.

### Vishing

* Phishing over the phone or Voice-over-IP \(VoIP\) phone systems. 
* Voice+Phishing

### Spear Phishing

* Involves targeting particular users, who may hold key positions, such as security officers, network or sys admins, or even managers and execs.
* Usually the attacker has done background work on the target.

# Privilege Escalation

* General type of attack - perpetrated on host after the attacker has gained access to the system.
* Usually takes advantage of vulnerabilities like weak encryption or auth methods, or even exploiting vulnerable software.
* Comprehensive system hardening program can help prevent privilege escalation attacks - keep security patches current, locking down configuration settings, allowing least privileges required on the system.

# Malicious Insider Threat

* Very complex to understand
* Can span different attack methods -  social engineering, technical attacks.
* Motivated by revenge, profit, or sabotage
* Mitigations include:
  * User education
  * Security clearances
  * Background checks

* Auditing is also key to detecting malicious insider attacks.

### Pharming

* Pharming is an attack in which the user is redirected to an attacker’s web site, regardless of the URL the user types into the browser.
* Requires config changes on the host

### DNS Poisoning

* DNS poisoning is an attack in which the entries in the DNS table are compromised, substituting known entries for bad entries.

### ARP Poisoning

* Involves sending false updates to a host, which it caches in its memory, resolving IP addresses to hardware \(or MAC addresses\).
* Sending false info to the host’s ARP cache may cause the communication with the malicious host instead of the legitimate one.
* Commonly used for network traffic sniffing - aggregating usernames/passwords/etc.



## Client-side Attacks

* Target vulnerabilities that exist on hosts, including configs and apps.
* Target web browsers.
* Include Cross-Site Scripting \(XSS\) attacks.

### Transitive Access

* Refers to passing on higher access privileges or permissions to a user. 
* Might happen if you inadvertently configure access rules too broad or to have excessive privileges in them.

### XMAS Attack

* Conducted by using specific flags in a TCP communications session.
* Flags such as SYN, FIN, URG, PSH - can be used to identify the type of host operating system on the target.
* Can be used to avoid Network IDSs

### Password Attacks

* Can be online or offline
* Offline - SAM or /etc/passwd file attacks
* \*Brute-force Attack\* - repeatedly guessing the user’s password.
* \*Dictionary Attack\* - attacks that are based on a predefined dictionary of common passwords. - quicker than brute force
* \*Hybrid Attack\* - both brute force and dictionary methods are used.
* \*Rainbow Attack\* - variation of a dictionary attack. - eliminates the step of hashing each word in list. Precomputed hashes

### Typo Squatting/URL Hijacking

* Makes use of incorrectly spelled or similar sounding URLs that the org may use to promote its business.

### Watering Hole Attack

* Has both social engineering and technical components to it.
* Attacker compromises a secondary system such as a website, and then waits for users to use the site which can then be used to send malware or other attacks down to unsuspecting users.



