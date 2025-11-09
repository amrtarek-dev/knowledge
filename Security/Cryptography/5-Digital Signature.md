Digital signatures provide a way to verify the authenticity and integrity of a digital message or document. Proving the authenticity of files means we know who created or modified them. Using asymmetric cryptography, you produce a signature with your private key, which can be verified using your public key. 

Only you should have access to your private key, which proves you signed the file. In many modern countries, digital and physical signatures have the same legal value.

Some articles use terms such as electronic signature and digital signature interchangeably. They refer to pasting an image of a signature on top of a document. This approach does not prove the document’s integrity, as anyone can copy and paste an image.



### Certificates: Prove Who You Are!

Certificates are an essential application of public key cryptography, and they are also linked to digital signatures. A common place where they’re used is for HTTPS.

he web server has a certificate that says it is the real one.

The certificates have a chain of trust, starting with a root CA (Certificate Authority). From install time, your device, operating system, and web browser automatically trust various root CAs. Certificates are trusted only when the Root CAs say they trust the organisation that signed them. In a way, it is a chain; for example, the certificate is signed by an organisation, the organisation is trusted by a CA, and the CA is trusted by your browser. Therefore, your browser trusts the certificate.

Let’s say you have a website and want to use HTTPS. This step requires having a TLS certificate. You can get one from the various certificate authorities for an annual fee. Furthermore, you can get your own TLS certificates for domains you own using [Let's Encrypt](https://letsencrypt.org/) for free. If you run a website, it’s worth setting up and switching to HTTPS, as any modern website would do.