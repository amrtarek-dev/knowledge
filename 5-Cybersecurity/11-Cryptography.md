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

#### Asymmetric encryption:
The use of a public and private key pair for encryption and decryption of data.

so the public key can be shared with any one want to communicate and the private key is used to decrypt the messages which is encrypted by the sender by the public key.

#### Symmetric encryption:
The use of a single secret key to exchange information.

> Establishing trust between the sender and receiver. is a common weakness for both symmetric and asymmetric encryption. 

#### Digital certificate
A file that verifies the identity of a public key holder.