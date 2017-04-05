# Cryptography

Supports one of the three major security goals: **Confidentiality**

**plaintext** - human readable information

**ciphertext** - non-human readable or interpretable information

**Encryption **- process of converting plaintext to ciphertext

Decryption - process of converting ciphertext to plaintext

Cryptography maintains the secrecy of data and also potentially the integrity of data \(via hashing\)

## Terms

Cryptanalysis - study of breaking encryption algorithms \(attempting to decrypt ciphertext without the appropriate key\)

Code - usually a concept that is a phrase/sentence \(e.g. "Thunder" -&gt; "Flash"\); usually requires a codebook to interpret

Cipher - character-by-character representation of a text

#### Data States

Data-at-Rest - data is in storage and not being accessed

Data-in-Flight - data is being transferred between two endpoints.

Data-in-Process - data is being processed by an application or some external running entity.

## Hashing

Hashing is part of cryptography but is not considered encryption.

Hashing is the process of creating a cryptographic fixed-length sum of an entity, aka **hash**

Hashes are static in length, independent of the input.

Hashing is a one-way process

![](/assets/crypt-1.png)

