
### Authenticating the server:

If you have used an SSH client before, you would know the confirmation prompt in the terminal output below.

Terminal

```shell-session
root@machine# ssh 10.10.244.173
The authenticity of host '10.10.244.173 (10.10.244.173)' can't be established.
ED25519 key fingerprint is SHA256:lLzhZc7YzRBDchm02qTX0qsLqeeiTCJg5ipOT0E/YM8.
This key is not known by any other name.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '10.10.244.173' (ED25519) to the list of known hosts.
```

In the above interaction, the SSH client confirms whether we recognise the server’s public key fingerprint. ED25519 is the public-key algorithm used for digital signature generation and verification in this example. Our SSH client didn’t recognise this key and is asking us to confirm whether we want to continue with the connection. This warning is because a man-in-the-middle attack is probable; a malicious server might have intercepted the connection and replied, pretending to be the target server.


### Authenticating the client
authentication uses public and private keys to prove the client is a valid and authorised user on the server. By default, SSH keys are RSA keys. You can choose which algorithm to generate and add a passphrase to encrypt the SSH key.

`ssh-keygen` is the program usually used to generate key pairs. It supports various algorithms, as shown on its manual page below.

Terminal

```shell-session
root@machine# man ssh-keygen
[...]
-t dsa | ecdsa | ecdsa-sk | ed25519 | ed25519-sk | rsa
Specifies the type of key to create. The possible values are “dsa”, “ecdsa”, “ecdsa-sk”, “ed25519”, “ed25519-sk”, or “rsa”.
[...]
```

The following is just for your information. At this stage, we recommend that you recognise their names only.

- **DSA (Digital Signature Algorithm)** is a public-key cryptography algorithm specifically designed for digital signatures.
- **ECDSA (Elliptic Curve Digital Signature Algorithm)** is a variant of DSA that uses elliptic curve cryptography to provide smaller key sizes for equivalent security.
- **ECDSA-SK (ECDSA with Security Key)** is an extension of ECDSA. It incorporates hardware-based security keys for enhanced private key protection.
- **Ed25519** is a public-key signature system using EdDSA (Edwards-curve Digital Signature Algorithm) with Curve25519.
- **Ed25519-SK (Ed25519 with Security Key)** is a variant of Ed25519. Similar to ECDSA-SK, it uses a hardware-based security key for improved private key protection.


When generating an SSH key to log in to a remote machine, you should generate the keys on your machine and then copy the public key over, as this means the private key never exists on the target machine using `ssh-copy-id`. However, this doesn’t matter as much for temporary keys generated to access CTF boxes.

The permissions must be set up correctly to use a private SSH key; otherwise, your SSH client will ignore the file with a warning. Only the owner should be able to read or write to the private key (`600` or stricter). `ssh -i privateKeyFileName user@host` is how you specify a key for the standard Linux OpenSSH client.


**Keys Trusted by the Remote Host**
The `~/.ssh` folder is the default place to store these keys for OpenSSH. The `authorized_keys` file in this directory holds public keys that are allowed access to the server if key authentication is enabled. By default on many Linux distributions, key authentication is enabled as it is more secure than using a password to authenticate. Only key authentication should be accepted if you want to allow SSH access for the root user.


> During CTFs, penetration testing, and red teaming exercises, SSH keys are an excellent way to “upgrade” a reverse shell, assuming the user has login enabled. Note that www-data usually does not allow this, but regular users and root will work. Leaving an SSH key in the `authorized_keys` file on a machine can be a useful backdoor, and you don’t need to deal with any of the issues of unstabilised reverse shells like Control-C or lack of tab completion.