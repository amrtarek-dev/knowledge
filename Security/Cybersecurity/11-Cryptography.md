The process of transforming information into a form that unintended readers can't understand.

Data can be hide by 2 process:
- Encryption: Hide the information
- Decryption: Unhide the information

First cryptographic method **Caeser's cipher** which depends on shifting letters in the Roman alphabet forward by a fixed number of spaces.

**Algorithm** is a set of rules to solve a problem

**Cipher** an algorithm that encrypts information.

**Cryptographic key** is a mechanism that decrypts ciphertext (the number of shifting in Caeser's cipher)

**Brute force attack**
A trial and error process of discovering private information.
Like shifting the Caeser's cipher letter with the 28 times to know the key.

Flow or Weakness of the Caeser's cipher:
- Brute force attack
- Single Key (easy to guess/know or stolen).

Brute force solution is the key length, 
and for the single key problem by having 2 keys, public, and private.

### Public Key Infrastructure (PKI)
An encryption framework that secures the exchange of information online.
2 steps process:
1. Exchange of encrypted information
	1. Asymmetric encryption (slow, but secure)
	2. Symmetric encryption (fast, but less secure)
	3. Or both
2. Establish trust using a system of digital certificates


Types of encryption:
#### Symmetric encryption:
The use of a single secret key to exchange information.
Algorithms:
- DES (Data Encryption Standard): in 1970 with 64-bit key length (56 bits only used for encryption)
- 3DES (Triple DES): Applies DES algorithm 3 times using 3 different (56-bit keys) (Limitation for the data which can be decrypted).
- AES (Advanced Encryption Standard): most symmetric algorithms today with keys 128, 192, or 256 bits.

#### Asymmetric encryption:
The use of a public and private key pair for encryption and decryption of data.
So the public for encryption and private for decryption.
Algorithms:
- **RSA** (Rivest Shamir Adleman) the name for the 3 creator of the algorithm from (Massachusetts Institute of Technology MIT) with key size: 1024, 2048, or 4096 bits. (for highly sensitive data)
- **DSA** (Digital Signature Algorithm) By NIST in 1990's is a complement of RSA in public key infrastructure (PKI) with key length 2048 bits.


> Establishing trust between the sender and receiver. is a common weakness for both symmetric and asymmetric encryption. 

#### Digital certificate
A file that verifies the identity of a public key holder.

### Generate Keys
- OpenSSL (Open source SSL): it has vulnerability in 2014  [Heartbleed bug](https://en.wikipedia.org/wiki/Heartbleed) which expose sensitive data in the memory of websites and applications.

### Obscurity is not security
A cryptographic system should not be considered secure if it requires around how it works.
A cipher must be proven to be unbreakable before claiming that it is secure According to [Kerckhoff’s principle](https://en.wikipedia.org/wiki/Kerckhoffs%27s_principle) except the private key.


### Hash function
An algorithm that produces a code that can't be decrypted.
It produce a unique identifier known as a hash value (digest).

It used as a way to determine the integrity of files and applications.
- MD5 (Message Digest 5) to verify that the message sent over a network matched its source file. (it convert data into 128-bit value (32 characters))

#### Non-repudiation
the concept that the authenticity of information can't be denied.

### VirusTotal
Is a database tool to analyzing suspicious files, domains, IPs and URLs.


### Hash Collision
When different inputs produce the same hash value.
Due to variable input size and fixed output file for MD5 (32 characters)

To avoid it, functions that generate longer values were needed.

## Secure Hashing Algorithms (SHA)
NIST approves 5 hash algorithms
- SHA-1 : 160 bits
- SHA-224: 224 bits
- SHA-256: 256 bits
- SHA-384: 384 bits
- SHA-512: 512 bits

``` bash
sha256sum filename
```

**Secure password storage** is saving the hash value of the password in the data base rather than the plaintext.

**Rainbow tables** is a file of pre-generated hash values and their associated plaintext.

**Salting** is a random string of characters that's added to dat before it's hashed to avoid the Rainbow table attack.