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

---

## Assymetric



