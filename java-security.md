# Java Security

[Java Secure Coding Practices](https://www.securecoding.cert.org/confluence/display/java/Security:+Introduction)

[Hashing Passwords with Java](https://www.securecoding.cert.org/confluence/display/java/MSC62-J.+Store+passwords+using+a+hash+function)

#### Cryptographic Hash Functions

| Lean On... | Avoid... \(birthday, collision attacks, crypto-broken\) |
| :--- | :--- |
| SHA-256 where possible \(SHA-2 also safe\) | MD5  |
| PBKDF2WithHmacSHA1 | SHA1 |
| PBKDF2WithHmacSHA512 |  |
| Bcrypt \(std. in Spring Security\) |  |



