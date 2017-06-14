# Control Frameworks

# Frameworks

#### ISO/IEC

Based on UK standard \(BS\) 7799 - Information Security Management Systems \(1995\)

* First adopted by ISO as ISO / IEC 17799 \(2000\)

* Evolved into ISO / IEC 27000 Series \(2005\)

* International Organization for Standardization \(ISO\)

* International Electrotechnical Commission \(IEC\)

* Documents:

  * 27001 Information Security Management Systems

  * 27002 Controls for an ISMS

  * 27003 IT Security Techniques

  * 27005 Risk Management

  * 27006 IT Certification and Accreditation

#### National Institute for Standards and Measures \(NIST\)

Recommended practices for computer security and risk management

* NIST SP800-30 Risk Assessment

* NIST SP800-37 Risk Management Framework

* NIST SP800-53 Rev4 Controls for Federal Info Systems

* NIST SP800-63 Rev2 Electronic Authentication Guide

* NIST SP800-81 Rev2 Secure DNS Deployment Guide

* NIST SP800-123 Guide to General Server Security

#### Generally Accepted Information Security Principles \(GAISP\)

International effort and vision for IT security

#### Committee of Sponsoring Organizations of the Treadway Commission \(COSO\)

Enterprise governance/risk based framework

* Ethics

* Internal Control

* Risk management

* Fraud

* Reporting

#### Control Objectives for Information and related Technology \(COBIT\)

IT security control model "harmonized" to operate within COSO

Developed by ISACA

#### Zachman Framework

Enterprise framework for viewing and defining an enterprise

#### Sherwood Applied Business Security Architecture \(SABSA\)

Security architecture with similar structure to the Zachman Framework

Risk driven

#### Information Technology Infrastructure Library \(ITIL\)

* IT service management

* Aligns IT services with business needs

* From UK Office of Government Commerce \(OGC\)

* Vendors Best Practices and Recommendations

---

# Applicable laws / Regulations

* **Legal Compliance **- imposed by US or other countries' laws

  * Sarbanes-Oxley \(SOX\)

  * Health Insurance Portability and Accountability Act \(HIPAA\)

  * Gramm-Leach-Bliley Act \(GLBA\)

* **Regulatory compliance **- imposed by industry

  * Payment Card Industry - Data Security Standard \(PCI DSS\)

#### PCI-DSS {#pci-dss}

Requirements for vendors to protect cardholder data

* Identifies 12 areas of required control

  * Firewalls

  * Change system defaults

  * Protect data at rest

  * Protect data in transit

  * Use antivirus protection

  * Use secure systems and app

  * Control Access - need to know

  * Unique user IDs

  * Physical Security

  * Track and Monitor Access

  * Test security systems

  * Establish policies



---

## Privacy and Common Law

* U.S. related privacy laws:

  * 46 US states and 4 US territories have enacted cyber crime laws requiring reporting a breach
  * Laws vary from state to state

* Employee privacy

  * Take the strongest legal position - no expectation of privacy

  * Monitor everything you can

  * Check with the local legal department

  * Commonly required: signed agreement, reminders, and routine monitoring not targeted.

* European Union Data Protection Directive

  1. Notice - subjects should be given notice when their data is being collected;

  2. Purpose - data storage reason

  3. Consent - data should not be disclosed without the owner's consent

  4. Security - collected data should be kept secure from any potential abuses.

  5. Disclosure - data subjects should be informed as to who is collecting their data

  6. Access - subjects should be allowed to access their data and make corrections

  7. Accountability - subjects should have a method to hold data collectors accountable for following the above principles

* Codified Legal System- France, Spain, South America \(Parts of Louisiana\)

  1. Rule based, written statutes. 2100 BCMesopotomia\(Modern Iraq\)

* Common Legal System- U.K., U.S.A., Australia

  1. Precedent based - ruling by judges rather than written statutes.

* Customary Legal System - Native American Indian, China, India

* Religious Legal System - defined by a deity

  1. Halakha \(jewish\), Sharia \(Islamic\)

* Hybrid/Mixed - combinations of two or more

  1. Like USA common legal system on a Native American reservation

### U.S. Common Legal System

**Civil \(Tort\) Law**

* * Contractual disputes, reclamation of loss, injuries

  * Determines liability often based on negligence

  * Smaller burden of proof/Preponderance of the evidence \(50.1%\)

  * Penalties are typically financial only.

**Criminal Law -**government protecting the public

* Larger burden of proof/Beyond a reasonable doubt \(99+%\)

* Penalties are more severe; Could be financial, jail term, or the death penalty.

**Administrative Law**- Government protecting the public from unscrupulous businesses

* FDA, FCC, FAA, OSHA, SOX, GLBA, HIPAA, etc.

* Import/Export Controls

  * International Traffic in Arms Regulations \(ITAR\)- Cryptography is an armament, and is treated as a weapon of war

  * Department of Commerce/Export Administration Regulations \(EAR\)

  * WassenaarArragement

  * Replaced the WWII COCOM in 1996 Coordinating Committee for Multilateral Export Controls

  * Prevent crypto from being exported to "dangerous" countries - usually the countries that maintain ties with terrorist organizations:Lybia, Iraq, Iran, North Korea

* Types of information being controlled

  * Crypto algorithm - Russia, Ukraine, Israel, China

  * Use of crypto within and in transit through the country

  * Medical info in transit through the country

  * Financial info in transit through the country

![](/assets/sec-controls-1.png)

![](/assets/sec-controls-2.png)

![](/assets/sec-controls-3.png)

Trans-border Info Flow

* Intellectual Property protection

  * Patent: protects the idea to benefit the inventor - 20 years

    * Must have utility, be novel, and non-obvious

    * Must reduce the invention to practice \(not just go to the moon, but how\)

    * Must prove monetary loss from violation to be awarded judgement

  * Copyright: protects the expression of the idea, not the idea - 75 years

    * Source code is the expression of the idea for an application

  * Trademark: icon or logo representing company, service, product

    * Symbols, sounds, etc.

  * Trade secret: corporate know-how

    * Must be adequately protected, have cost the own something to develop it, provide competitive value

    * NDA, numbered copies, secure storage, logging access, other controls

    * Does not require registration, exposure.

  * Digital Rights Management \(DRM\)- protect digital content from unauthorized usage and repro

    * Targets digital movies, music, audio books

    * Restrictive licensing agreements

    * CD keys / limited install or activation

    * Encryption / scrambling

    * Persistent authentication \(always on DRM\)

    * Program Manipulation \(if violation is suspected\)

* World Intellectual Property Organization Copyright Treaty \(WCT 1996\) and the US Digital Millenium act

* Controversial - can prohibit legitimate use, fair use \( for education\)

* Electronic Frontier Foundation and Free Software Foundation oppose DRM

* A subset of DRM: Data Loss Prevention \(DLP\)

* Metadata keyword or watermark filtering

* Software Licensing and Piracy

  * Ethical enterprises would disallow use of unlicensed software

  * Licenses must be managed - software library

    * site license

    * per server license

    * per seat \(user\) license

    * annual subscription

  * Shareware / crippleware / bloatware \(Usually disallowed\)

  * Report piracy to the Business Software Alliance

* [Payment Card Industry Data Security Standard \(PCI DSS\)](#pci-dss)

* Auditing

  * Systems must be routinely audited \(internally\) and often by external, third party auditors - Certified, unbiased

  * Proof of auditing required

  * Follow established auditing procedures, methodologies

  * Preventive mechanisms added and remediation for findings.

  * Reporting

    * Results of internal and external audits must be reported

      * Self Assessment Questionnaire \(SAQ\)

      * Attestation of Compliance \(AOC\)

      * Breaches and non-compliance must be reported.

  * Metrics

    * Evaluating the effectiveness of your security

    * Should be recorded and reported over time to:

      * Identify trends

      * Evaluate effectiveness of controls in place

      * Identify required adjustments and additional controls.

    * Examples:

      * \# of policy violations total, reported vs detected - weekly, monthly

      * Patching latency: OS, Applications

      * Baseline coverage: Systems without AV,personal FW, OS and application updates

      * Designed in security controls vs afterthought addition

      * \# of successful exploits of software vulnerabilities

      * \# of true positives IDS alerts vs false positive alerts

      * \# of virus infections vs virus alerts

      * \# of serious vulnerabilities reported by scanner

      * Platform compliance scores / Center for Internet Security Benchmarks

  * Ethical Standards

    * Senior management must impart their ethical standards into the governance framework

    * Must be established in policies, practices, and awareness training.

    * ISC^2 Code of ethics

      * Protect society, the commonwealth, and the infrastructure

      * Act honorably, honestly, justly, responsibly, and legally

      * Provide diligent and competent service to principals

      * Advance and protect the profession.

    * The Computer Ethics Institute - 10 commandments

      * Use a Computer to harm other people

      * Interfere with other people's computer work

      * Snoop around in other people's computer files

      * Use a computer to steal

      * Use a computer to bear false witness

      * Copy or use proprietary software for which you have not paid

      * Thou shalt not use other people's computer resources without authorization

      * ...

    * Internet Architecture Board \(IAB\) - RFC 1087

      * Unethical to:

        * Seek to gain unauthorized access to the resources of the Internet

        * Disrupt the intended use of the Internet

        * Waste resources \(people, capacity, computer\)

        * ...

    * Computer crime - breach of laws and regulations - not a breach of policy

    * The role of computer in computer crime \( 3 ways \)

      * The target\* system - the system being breached

      * The attacker system - the system used by the attacker

      * An incidental system - a system used during the act - used to develop the exploit code, store stolen IP, etc.

## Computer Crimes

* Data Theft

  * Financial Account, medical info

  * PII - Identity Theft

  * Intellectual property, trade secrets

  * Ransomware

* Denial of Service \(DoS\)

* Data alteration

  * Fraud, cooking the books

* Salami Attack - a small unnoticeable slice, taken from many.

* System takeover

  * Command and control over machine

  * Botnet, Army of Zombies

  * Ransom-ware

* Child pornography

* Social Engineering

  * Phishing

  * Scams

  * Shoulder surfing

* Dumpster Diving

  * Not usually a crime, but incurs losses

* Computer Crime attackers

  * Script kiddies

  * Insider / Coworker

  * Partners

  * Organized Crime

  * Corporate Espionage

  * Governments

  * Hacktivists

  * Skilled Professional - APT

  * Proof of concept trials \(Morris worm\)

  * Social Engineer

  * Terrorists

* Computer crime attackers - Social engineering

  * Tricks the unsuspecting target by eliciting unwarranted trust to gain some unauthorized access

  * Techniques

    * Offering assistance

    * Requesting assistance, sympathy

    * Appealing to human desire \(Greed, lust, etc.\)

    * Delegated authority or trust

    * Tailgating, shoulder surfing

    * Busy and bothered

    * Passive recon

    * Trusted insider

    * Pre-texting

    * Phishing

* Difficulties in prosecuting computer crime

  * Enterprises don't want to report the crime

    * Bad PR

    * Loss of assets

  * Formalizes losses - larger lawsuits, liabilities

  * Evidence is complex, intangible, difficult to collect and present

  * Laws are different in different countries

  * Jurisdictional issues / Lack of cooperation

  * Attackers were juveniles -- Not prosecutable \(not so true today\)

  * Lack of investigative skills and manpower

  * Computer crime scene

  * Evidence collection, handling, analysis, admissibility, presentation

  * Forensics

  * Legal skills

  * Hesitation to try new type of case and failing

    * Establishes a new precedent -- the wrong way

* Cloud, outsourced services, SLA's, contractors, vendors, clients

  * If you share data with any third parties, you must formally govern their access, processing, use, storage, and transmission of your data

  * Must meet or exceed your policies, standards of compliance \(legal and regulatory\), ethics

  * Their compliance may be required by laws and regulations

  * Signed agreements that define requirements, compliance, monitoring, auditing, and liabilities if compliance violations

  * Must be monitored, audited \(internal/external\)

  * Certifications may be required

  * Cooperative response requirements in case of breach



