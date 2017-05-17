ublic Key Infrastructure \(PKI\)

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





