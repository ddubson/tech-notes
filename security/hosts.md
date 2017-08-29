# Hardening Hosts

How to protect hosts from external threats \(mitigating threats\).

Hosts can be defined as: servers, desktops, laptops, tablets, IoT devices, smartphones, etc.

---

Hardening refers to locking down a host so that it contains only the bare minimum functionality it needs to function properly, to be update with patches, to have user and account settings properly set, etc.

## Techniques

#### Secure Configuration

Out of the box installations of systems are usually not configured to be secure or hardened.

The host needs to be reconfigured to address security issues.

#### Disabling Unnecessary Services

All hosts run services to maintain the system. Unnecessary services can also be configured to run by default.

e.g. home desktops or laptops have no need to run FTP servers and so should be removed or turned off.

#### Practice Management Interfaces and Apps

Principles of least privilege apply to management interfaces/apps. Users should not be able to access computer management consoles that they are not authorized to access.

#### Password Protection

Apps, utilities, and hosts themselves should be secured with a strong password \(password expiry practices, no re-use of old passwords, frequent password changes, rules against password sharing, etc.\)

#### Disabling Unnecessary Accounts

Disabling guest accounts or accounts that are not used should always be disabled to reduce the attack surface for potential system intrusion.

---

### Operating System Hardening

Hardening an OS means: configuring the OS and setting security options appropriately.

Focus on **privilege levels and groups \(Admins and standard users\)** - access to storage media, shared files/folders, rights to change system settings.

#### Patch Management

Download latest patches as they become available on home desktops and laptops

Patch management process should be in place for enterprise hosts.

* Patches are reviewed for their applicability
* Each patch needs to be understood what it fixes
* May be done via patch management software
* Each patch installed should be logged for audit purposes

#### Trusted OS

Specialized version of OS, created and configured for high security environments.

May require special hardware to run on.

Examples are: Trusted Solaris, SE Linux, AIX 5

#### Anti-Malware

Anti-malware protection products

---

## Host Hardening Measures

#### Whitelisting vs Blacklisting Apps

**Blacklisting** involves an admin adding an undesirable piece of software or an app to a list on a content filtering device so that users are not allowed to download or execute particular apps

**Whitelisting** whitelist contains an app that are allowed on the network or allowed to be installed on the system and denied to everything else.

---

## Host-based firewalls and intrusion dection

Host-based firewalls and intrusion detection systems are usually software-based.

* Filter traffic coming into the host from network based on rules that inspect traffic
* Intrusion Detection System \(IDS\) serve to detect patterns of malicious traffic.
* Firewalls should follow principle of least privilege.
* Firewalls should be baselined for normal traffic patterns.
* Firewalls and IDS should be updated regularly for new attack signatures

---

## Hardware Security

Physically securing hosts mitigates physical threats to hardware.

* Prevents theft, or destruction of hardware.
* Store laptops or mobile devices in a secure cabinet,
* Create policies around physical equipment handling
  * Inventory management

---

## Maintaining Host Security Posture

Formal programs should be in place to keep hosts secure including policies, procedures, and configuration control.

* **Initial Baseline Configuration**
  * More efficient maintenance of hardware
  * Easier to problem solve when issues arise
  * Uniform policy requirements for hosts
  * Split up policies based on types of users in the organization
    * i.e. admins, standard users
* **Continuous Security Monitoring**
  * Track configuration of the system and alert admins if changes occur
  * Adds to transparency of host events
  * Automated event aggregation and reporting \(e.g. SNMP\)
* **Remediation**
  * 





