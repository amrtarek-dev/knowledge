Hash functions are different from encryption. There is no key, and it’s meant to be impossible (or computationally impractical) to go from the output back to the input.

A hash function takes some input data of any size and creates a summary or **digest** of that data. The output has a fixed size. It’s hard to predict the output for any input and vice versa. Good hashing algorithms will be relatively fast to compute and prohibitively slow to reverse, i.e., go from the output and determine the input. Any slight change in the input data, even a single bit, should cause a significant change in the output.

Let’s check an example. In the terminal below, we can see two files; the first contains the letter T, while the second contains the letter U. If you check T and U in an ASCII table or using `hexdump`, you will notice that the two letters differ by a single bit.

- The letter T is `54` in hexadecimal, i.e., `01010100` in binary.
- The letter U is `55` in hexadecimal, i.e., `01010101` in binary.

Consequently, the following two files differ by a single bit. However, if we compare their 
MD5 (Message-Digest Algorithm 5) hashes, their 
SHA1 (Secure Hash Algorithm 1) hashes, or their 
SHA-256 (Secure Hash Algorithm 256) hashes, 
we will notice that they are entirely different. 

```shell-session
strategos@g5000 ~> cat file1.txt 
T⏎
strategos@g5000 ~> cat file2.txt 
U⏎   
strategos@g5000 ~> hexdump -C file1.txt 
00000000  54                                                |T|
00000001
strategos@g5000 ~> hexdump -C file2.txt 
00000000  55                                                |U|
00000001
strategos@g5000 ~> md5sum *.txt
b9ece18c950afbfa6b0fdbfa4ff731d3  file1.txt
4c614360da93c0a041b22e537de151eb  file2.txt
strategos@g5000 ~> sha1sum *.txt
c2c53d66948214258a26ca9ca845d7ac0c17f8e7  file1.txt
b2c7c0caa10a0cca5ea7d69e54018ae0c0389dd6  file2.txt
strategos@g5000 ~> sha256sum *.txt
e632b7095b0bf32c260fa4c539e9fd7b852d0de454e9be26f24d0d6f91d069d3  file1.txt
a25513c7e0f6eaa80a3337ee18081b9e2ed09e00af8531c8f7bb2542764027e7  file2.txt
```

The output of a hash function is typically raw bytes, which are then encoded. Common encodings are base64 or hexadecimal. `md5sum`, `sha1sum`, `sha256sum`, and `sha512sum` produce their outputs in hexadecimal format. 

Remember that hexadecimal format prints each raw byte as two hexadecimal digits.

> Hashing helps protect data’s integrity and ensure password confidentiality.


As per good security practices, a server does not record your password; it records the hash value of your password. 
Whenever you want to log in, it will calculate the hash value of the password you submitted with the recorded hash value. 
Similarly, when you log into your computer, hashing plays a role in verifying your password. 
You interact more indirectly with hashing than you would think, and almost daily in the context of passwords.