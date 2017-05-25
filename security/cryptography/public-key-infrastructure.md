# Public Key Infrastructure \(PKI\)

## Concepts

Amalgamation of multiple techniques, algorithms, and processes that **create and manage an infrastructure for managing digital certificates throughout their lifecycle.**

Lifecycle includes:

* Issuance of certificates
* Use of certificates
* Disposal of certificates

Digital Certificates are used to identify individuals, using crypto concepts.

# Keys, Algorithms, and Standards

PKI uses a confluence of assymetric and symmetric algorithms, as well as hashing algorithms \(using concept of **hybrid cryptography**\)

Using:

* assymetric algoritms solves for **key exchange**
* symmetric algorithms solve for **speed of encryption/decryption on large amount of data \(**session keys can be encrypted via symmetric alg. but exchanged via assymetric methods\)
* hybrid approach solves for **confidentiality,** but does not ensure authenticity or integrity or non-repudiation
* hashing algorithms solve for **authenticity, integrity, and non-repudiation**

### Algorithms

PKI algorithms include:

* Symmetric:
  * AES \(Advanced Encryption Standard\)
* Assymetric
  * RSA \(Key Generation\)
  * Diffie-Hellman \(Key Exchange\)
* Hashing
  * MD5
  * RIPEMD \(RACE Integrity Primitives Evaluation Message Digest\)
  * SHA \(Secure Hash Algorithm\)

### Standards

Standards govern the construction and formatting of digital certificates.

#### **X.509 Standard**

Managed by International Telecommunication Union - Telecommunication Standardization Sector \(ITU-T\)\)

X.509 describes:

* how certificates are constructed
* what information they contain
* what their uses are
* formatting
* processes involved with issuing certificates
* other processes involved in certificate lifecycle

#### PKCS \(Public Key Cryptography Standards\)

Managed and developed by RSA Security

PKCS describes:

* certificate construction

**PKCS \#7** file is a digital certificate used to sign or encrypt messages \(e.g. email\)

**PKCS \#12** file contains public and private keys, encrypted for secure storage.

---

## PKI Services

### Key Generation and Exchange

Key generation is the act of creating a private and public key pair, which is issued to an individual based on confirmed identity.

RSA is the most popular key generation algorithm.

Key exchange is a process that assists in creation and secure exchange of symmetric keys \(session keys\) that are used for that communication session only.

After creation, public and private keys are used to encrypt/decrypt session keys once they are transmitted and received by both parties.

#### Non-Repudiation

Someone cannot deny that they took a particular action -- their identity is positively verified.

Non-repudiation in PKI is assured via the use of public/private keys.

#### Message Integrity

Using hashing algos like SHA-512, messages can be hashed to create unique fingerprints that can be checked before and after transmission.

Messages can be changed due to non-malicious causes like bad transmission mediums potentially dropping bits of data.

PKI hashes the message and encrypts both the message and the hash and transmits the payload.

#### Digital Signatures

A person encrypting a message with private key can let anyone with a public key decrypt it, so that leads to verifying that the origin of the message is the possessor of the private key.

## Digital Certificates

Simple electronic files that follow a format \(X.509, PKCS\)

Can have many different extensions \(.cer, .pem\)

Might have multiple types serving a specific function within PKI

Certificates contain a variety of information, including:

* Public Key 
* Identity of person
* Issuing Organization
* Valid Dates
* Functions for certificate

### Certificate Registration

Lifecycle begins when a user registers to receive a certificate.

Person must provide valid information and identification to the **Certificate Authority \(CA\)** 

CA must authenticate the user's personal information

Valid forms of identification can be:

* Driver's License
* Birth Certificate
* Passport
* Photographs
* etc.

CA makes a decision to issue or deny a certificate



