Most web applications need to verify a user’s password at some point.
Storing these passwords in plaintext is a very insecure security practice.

We will visit **three insecure practices** when it comes to passwords:

- Storing passwords in plaintext
- Storing passwords using a deprecated encryption
- Storing passwords using an insecure hashing algorithm

#### **Storing Passwords in Plaintext**

Quite a few data breaches have leaked plaintext passwords. You’re probably familiar with the “rockyou.txt” password list on Kali Linux, among many other offensive security distributions. This password list came from RockYou, a company that developed social media applications and widgets. They stored their passwords in **plaintext**, and the company had a data breach. The text file contains over 14 million passwords. You can find `rockyou.txt` in the `/usr/share/wordlists` directory.

#### **Using an Insecure Encryption Algorithm**

Adobe’s notable data breach was slightly different. Instead of using a secure hashing function to store the hash values of the passwords, the company used a deprecated encryption format. Furthermore, password hints were stored in plain text, sometimes containing the password itself. Consequently, the plaintext password could be retrieved relatively quickly.

#### **Using an Insecure Hash Function**

LinkedIn also suffered a data breach in 2012. LinkedIn used an insecure hashing algorithm, the SHA-1, to store user passwords. 
Furthermore, no password salting was used. **Password salting** refers to adding a **salt**, i.e., a random value, to the password before it is hashed.

