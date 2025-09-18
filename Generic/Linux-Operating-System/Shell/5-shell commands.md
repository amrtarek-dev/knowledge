
## expr
To evaluate expression
``` bash
expr 3 - 1
```

## tr
Translates text command from one set of characters to another.
- first parameter to the `tr` command is the input set of characters
- second parameter is the output
``` bash
cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"
```
This will shift all character in the .leftShift3 file to left by 3


## OpenSSL
For encrypt and decrypt of files
``` bash
openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
```
- aes-256-cbc: decrypt the AES key length of 256
- -pbkdf2: to add extra security to the key
- -a: indicates the desired encoding for the output
- -d: indicates decrypting
- -in: input file
- -out: output file
- -k: the password

## &
This operator allows you to run commands in the background of your terminal

## &&
This operator allows you to combine multiple commands together in one line of your terminal.
The command after && will only execute if the command before && success.

## ||
The same like && but if the command before the sign fail the command after will execute.
