# Algorithms

## Symmetric

### DES - Data Encryption Standard

Older, obsolete standard

Algorithm used in DES is called **Lucifer** \(developed by IBM\)

Operated on 64-bit blocks

* 8 bits were used for computational overhead
* 56 bit key size

DES uses 5 different modes \(defined method that determines how plaintext block is input and changed to produce ciphertext\)

* **Electronic Code Book \(ECB\)** mode is simplest
  * Each 64-bit block will produce the same output for a given input \(predictable\)
* **Cipher Block Chaining** **\(CBC\)**
  * Stronger encryption due to Initialization Vector \(IV\) and XOR Function \(less predictable\)
* **Cipher Feedback \(CFB\)**
  * plaintext is divvied up into different bit-size segments and each output is fed back into process and used as IV in subsequent block of plaintext.
* **Output Feedback \(OFB\)**
  * Similar to CFB but uses 64-bit IV that are fed back into process for each subsequent block of plaintext
* **Counter \(CTR\)** mode \(fastest\)
  * random 64-bit block is used as IV
  * incremented for every subsequent block by specific number or counter.

DES uses **16 rounds** for each mode.

### 3DES \(Triple DES\)

Later iteration of DES designed to fix problems in original standard.

3DES puts plaintext blocks through DES encryption 3 times.

Uses three 56-bit key bundles.

3DES uses Encrypt-Decrypt-Encrypt \(EDE\) method with 3 separate keys during the three stages.

### Advanced Encryption Standard \(AES\) {#toc_0}

* Established in 2001 by NIST to be official encryption standard for U.S. Govt.
* Based on the
  **Rijndael Algorithm**
* Symmetric block cipher that can use block sizes of 128 bits with key sizes of 128, 192, 256 bits.
  * 10 rounds for 128-bit keys
  * 12 rounds for 192-bit keys
  * 14 rounds for 256-bit keys
* Can use different modes for encryption/decryption.
* Most attacks on AES are theoretical \(side-channel attacks\)

### Blowfish {#toc_1}

* Block cipher created in 1993 \(Bruce Schneier\)
* Based on 64-bit blocks, with key sizes from 32 bits to 448 bits.
* Uses 16 rounds of encryption
* Susceptible to birthday attacks \(in HTTPS context\)
* Susceptible to collision attacks in CBC mode \(SWEET32\)

### TwoFish

* Replacement for Blowfish
* Symmetric block algorithm with 128-bit block size.
* Keys of 128-bit, 192-bit, or 256-bit keys.
* Uses 16 rounds of encryption.

### RC4

* Streaming cipher
* Invented by Ron Rivest
* Uses one round of encryption 
* Key sizes from 40 to 2048 bits in length.
* Most popular in wireless encryption
* Currently cryptographically vulnerable and is not recommended for use \(RFC 7465 - RC4 eliminated from TLS\)    

---

## Assymetric {#toc_4}

### RSA {#toc_5}

* Used to create a public-private key pair.
* Generates keys via factoring two very large prime number
* One round of encryption
* Key sizes from 1,024 to 4,096 bits.
* Defacto assymetric algorithm today

### Diffie-Hellman {#toc_6}

* aka D-H or DHE -- series of key exchange protocols and variants.
* D-H provides secure key exchange.
* Elliptic Curve Diffie-Hellman Exchange \(ECDHE\) is a variant of DHE based upon elliptic curve cryptography.

### PGP/GPG {#toc_7}

* PGP -&gt; Pretty Good Privacy - crypto application and protocol suite.
  * Can use both assymetric and symmetric keys for a wide variety of operations:
    * bulk encryption
    * data-at-rest encryption
    * key-pair generation
    * key exchange
* Uses "web of trust" instead of public key infrastructure \(PKI\)
* GPG is open source equivalent \(Gnu Privacy Guard\)

### Elliptic Curve Cryptography \(ECC\) {#toc_8}

* ECC is an assymetric method of cryptography based on algebraic structure of elliptic curves over finite fields.
* Applies to encryption and digital signatures.
* Widely implemented in smart phones

### ElGamal {#toc_9}

* Assymetric algorithm for digital signatures and encryption.
* Widely used in open standards, including PGP/GPG
* US Govt. Digital Signature Algorithm \(DSA\) is based on ElGamal signature scheme

---

## Hashing Algorithms {#toc_10}

### Message Digest 5 {#toc_11}

* Developed by Ron Rivest in '91
* Generates a 128-bit hash, 32-hex long
* Replaced MD4
* Susceptible to colision attacks
* Should not be used in secure environments

### SHA {#toc_12}

* Secure Hash Algorithm \(SHA\) - series of hash functions sponsored by NIST.
* SHA-1 is a 160-bit algorithm, producd 40 character hashes.
* SHA-2 is two separate algorithms
  * SHA-256
  * SHA-224
  * SHA-512
  * SHA-384
* SHA-3 - based on Keccak hashing function



