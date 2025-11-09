- **Plaintext** is the original, readable message or data before it’s encrypted. It can be a document, an image, a multimedia file, or any other binary data.
- **Ciphertext** is the scrambled, unreadable version of the message after encryption. Ideally, we cannot get any information about the original plaintext except its approximate size.
- **Cipher** is an algorithm or method to convert plaintext into ciphertext and back again. A cipher is usually developed by a mathematician.
- **Key** is a string of bits the cipher uses to encrypt or decrypt data. In general, the used cipher is public knowledge; however, the key must remain secret unless it is the public key in asymmetric encryption. We will visit asymmetric encryption in a later task.
- **Encryption** is the process of converting plaintext into ciphertext using a cipher and a key. Unlike the key, the choice of the cipher is disclosed.
- **Decryption** is the reverse process of encryption, converting ciphertext back into plaintext using a cipher and a key. Although the cipher would be public knowledge, recovering the plaintext without knowledge of the key should be impossible (infeasible).

Cryptography’s history is long and dates back to ancient Egypt in 1900 BCE.
- Caesar Cipher from the first century BCE.
- The Vigenère cipher from the 16th century
- The Enigma machine from World War II
- The one-time pad from the Cold War


## Encryption Types
- Symmetric: using the same key to encrypt and decrypt (private key cryotography)
	- DES (Data Encryption Standard): was adopted as a standard in 1977 and uses a 56-bit key. With the advancement in computing power, in 1999, a DES key was successfully broken in less than 24 hours, motivating the shift to 3DES.
	- 3DES (Triple DES): is DES applied three times; consequently, the key size is 168 bits, though the effective security is 112 bits. 3DES was more of an ad-hoc solution when DES was no longer considered secure. 3DES was deprecated in 2019 and should be replaced by AES; however, it may still be found in some legacy systems.
	- AES (Advanced Encryption Standard): was adopted as a standard in 2001. Its key size can be 128, 192, or 256 bits.
- Asymmetric: uses a pair of keys, one for encryption and the other for decrypt, encrypts the data using the public key; hence, it is also called **public key cryptography**.
	- RSA ( ) uses 2048-bit, 3072-bit, and 4096-bit keys; 2048-bit is the recommended minimum key size.


Cipher depend on math so the 2 mathematical operations that are used in various algorithms:
- XOR operation
- Modulo operation

### XOR
exclusive OR -> 1 in difference and 0 in same.
One key property is that applying XOR to a value with itself results in 0, and applying XOR to any value with 0 leaves it unchanged. This means A ⊕ A = 0, and A ⊕ 0 = A for any binary value A. Additionally, XOR is commutative, i.e., A ⊕ B = B ⊕ A. And it is associative, i.e., (A ⊕ B) ⊕ C = A ⊕ (B ⊕ C).

XOR can be used as a basic symmetric encryption algorithm.

Consider the binary values P and K, where P is the plaintext, and K is the secret key. The ciphertext is C = P ⊕ K.

Now, if we know C and K, we can recover P. 

We start with C ⊕ K = (P ⊕ K) ⊕ K. But we know that (P ⊕ K) ⊕ K = P ⊕ (K ⊕ K) because XOR is associative. 

Furthermore, we know that K ⊕ K = 0; consequently, (P ⊕ K) ⊕ K = P ⊕ (K ⊕ K) = P ⊕ 0 = P. 

In other words, XOR served as a simple symmetric encryption algorithm. In practice, it is more complicated as we need a secret key as long as the plaintext.

### Modulo
commonly written as % or as _m__o__d_. The modulo operator, _X_%_Y_, is the **remainder** when X is divided by Y.

You need to work with large numbers when solving some cryptography exercises. If your calculator fails, we suggest using a programming language such as Python. Python has a built-in `int` type that can handle integers of arbitrary size and would automatically switch to larger types as needed. Many other programming languages have dedicated libraries for big integers. If you prefer to do your math online, consider [WolframAlpha](https://www.wolframalpha.com/).

- 25%5 = 0 because 25 divided by 5 is 5, with a remainder of 0, i.e., 25 = 5 × 5 + 0
- 23%6 = 5 because 23 divided by 6 is 3, with a remainder of 5, i.e., 23 = 3 × 6 + 5
- 23%7 = 2 because 23 divided by 7 is 3 with a remainder of 2, i.e., 23 = 3 × 7 + 2

An important thing to remember about modulo is that it’s not reversible. If we are given the equation _x_%5 = 4, infinite values of _x_ would satisfy this equation.

The modulo operation always returns a non-negative result less than the divisor. 
This means that for any integer _a_ and positive integer _n_, the result of _a_%_n_ will always be in the range 0 to _n_ − 1.