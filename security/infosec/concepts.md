# CIA Triad - Confidentiality, Integrity, Availability

* To protect Valuable Info Assets
* **Confidentiality **
  * Keeping secrets secret
  * Privacy - confidentiality of personally identifiable info \(PII\)
  * Secrecy - the unauthorized are unaware of the comm. or info asset
  * Access controls and cryptography \(locked doors, encrypted\)
    * Can't access
    * Can't read if access is gained
  * Restrict access to data
  * Can also be tunneled
  * Typically uses cryptography
  * Can be brute force attacked.
* **Integrity **
  * The accuracy, authenticity, completeness, and consistency of info
  * Integrity protection - keep the bad guys away from the data
    * Access controls and crypto
  * Integrity verification - verify accuracy of the data at time of use
    * Hashing / message digests
  * Occurs with checksums and FCS
  * Can also include origin authenticity with additional mechanisms
    * Least privilege
    * Separation of duties
    * Rotation of duties
    * Forced vacations
* **Availability **
  * Having the info accessible when it is needed.
  * Redundancy, co-location, fault tolerance

## Additional Elements

* **Identification** - identifying a person before one can access a restricted system.
  * Presenting user credentials
* **Authentication** - process of gaining access to a system or facility.
  * Credentials are validated after being presented
* **Authorization** - process of granting a user or entity the appropriate permissions, rights, and privileges to the system.
* **Auditing** - implemented by recording the actions of users or other entities when they interact with system or data.
* **Accountability** - the process of holding users accountable for their actions.
  * Serves as a deterrent from committing security policy violations if they know their actions are being recorded/audited.
    * Used to punish/sanction users who attempt to or successfully violate sec policies.
* **Non-Repudiation** - users cannot deny that they have performed an action with regard to the system or data.

![](/assets/infosec-concepts-1.png)

## SECURITY CONCEPTS

### Control

* Security mechanism that is implemented either to increase security or to make up for a short fall in security.
* Administrative \(managerial\) controls - applied through policy, procedures, and so on.
  * e.g. a policy on proper care and use of a computer
* Technical Controls \(logical controls\)
  * Firewalls, file and folder permissions, ACLs
* Physical Controls \(operational controls\) - address physical sec
* Functional Categories of Control
  * Preventative
  * Deterrent
  * Detective
  * Corrective
  * Compensating
  * Recovery

### Defense-in-Depth

* Layered security
* Multiple levels of defense within network and host environments

### Data Sensitivity and Classification

* Data Sensitivity relates to the importance, criticality, and sensitivity of the data stored on your systems.

### Principle of Least Privilege

* All users should be granted only the least of privileges they need to do their jobs and no more.

### Separation of Duties

* Administrative control, related to policy
* A single individual should not perform all critical or privileged level duties.
* Ensures that no single individual can perform sufficiently critical or privileged actions that could seriously damage a system, operation, or org.

### Multi-person Control

* More than one person is required to accomplish a specific task or function.

### Mandatory Vacations

* requires individuals to take vacations at various times of the year, so that another individual can fulfill the vacationers' responsibilities and their duties can be audited.
* Used to detect fraud

### Job Rotation

* periodically switches people around to work in different positions.

## DUE DILIGENCE AND DUE CARE

**Due Diligence** - 'thinking responsibly' - when an org has performed the research and investigated issues that could cause security or safety problems.

**Due Care** - 'acting responsibly' - when an org has done all it can to prevent potential security incidents. Put controls in place \(e.g. policies\) and actively took steps to mitigate damage from incidents

