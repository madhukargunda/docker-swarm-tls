# docker-swarm-tls


## What is PEM file

```
- PEM or Privacy Enhanced Mail is a Base64 encoded DER certificate. 
- PEM certificates are easily translated into readbale format when we open in editors.
- When we open the PEM Certificates it contains the it contains very distinct headers and footers.
- By Reading the Headers and Footers we can easily distingush type of the file.
- PEM Format contains the 
    - HEADER
    - BODY
    - FOOTER

The header and footer is what identifies the type of file, however be aware that not all PEM files necessarily need them.

-----BEGIN CERTIFICATE REQUEST----- and -----END CERTIFICATE REQUEST----- show a CSR in PEM format.
-----BEGIN RSA PRIVATE KEY----- and -----END RSA PRIVATE KEY----- show a private key in PEM format.
-----BEGIN CERTIFICATE----- and -----END CERTIFICATE----- show a certificate file in PEM format.

Example :-

The below one is the example client requesting CA to sign.

-----BEGIN CERTIFICATE REQUEST-----
MIIB9TCCAWACAQAwgbgxGTAXBgNVBAoMEFF1b1ZhZGlzIExpbWl0ZWQxHDAaBgNV
BAsME0RvY3VtZW50IERlcGFydG1lbnQxOTA3BgNVBAMMMFdoeSBhcmUgeW91IGRl
Y29kaW5nIG1lPyAgVGhpcyBpcyBvbmx5IGEgdGVzdCEhITERMA8GA1UEBwwISGFt
aWx0b24xETAPBgNVBAgMCFBlbWJyb2tlMQswCQYDVQQGEwJCTTEPMA0GCSqGSIb3
DQEJARYAMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCJ9WRanG/fUvcfKiGl
EL4aRLjGt537mZ28UU9/3eiJeJznNSOuNLnF+hmabAu7H0LT4K7EdqfF+XUZW/2j
RKRYcvOUDGF9A7OjW7UfKk1In3+6QDCi7X34RE161jqoaJjrm/T18TOKcgkkhRzE
apQnIDm0Ea/HVzX/PiSOGuertwIDAQABMAsGCSqGSIb3DQEBBQOBgQBzMJdAV4QP
Awel8LzGx5uMOshezF/KfP67wJ93UW+N7zXY6AwPgoLj4Kjw+WtU684JL8Dtr9FX
ozakE+8p06BpxegR4BR3FMHf6p+0jQxUEAkAyb/mVgm66TyghDGC6/YkiKoZptXQ
98TwDIK/39WEB/V607As+KoYazQG8drorw==
-----END CERTIFICATE REQUEST-----

```

### CERTIFICATE EXTENTIONS

```
- .crt used for certificate extention.
- certificates can encoded as binary 
      DER format 
      ASCII PEM (BASE 64 format) .
- .cer is the alternate extention of the .crt introduced by microsoft.
- .cer fomrat also contains the both the DER and ASCII PEM .
- .cer is introduced by the microsoft.
- .key extention is also used for representing the private key and public key 


```

### There are four types of certificate manipulation
  
  ```
  - VIEW
  - TRANSFORM
      PEM to DER
      DER to PEM
  - COMBINATION
  - EXTRACTION
  
  
  ```
  
  ### HOW DIGITAL SIGNATURE WORKS
  
  ```
  - Digital signature is used to check the data integrity and authenticity of the sender and Receiver
  - In Digital Signature there are two keys invloved.
      a.Public Key
      b.Private Key
  - Digital signatures uses the asymetrickey cryptography.
  - Sender will creates the Publick key and Private Key .
  - Sender gives the his publick key to receiver
  - Sender will creates the memo.
  - Sender will generates the Message digest using some hasing algorithom
  - Then sender will encrypts the Message Digest using the Sender private key 
  - The Encrypted message called as Digital Signature of that particular memo.
  - When Recevier receives the message and Receiver decrypts the message digest using sender 
    public key and using the memo he generates the message digest .
  - If both message digest are same then message not tampred.
  
  ```
  
  ### WHAT IS DIGITAL CERTIFICATE / PUBLIC KEY CERTIFICATE
  
  ```
  - First sender creates the pair of keys ,Public key and Private Key
  - Private key sender will keeps
  - Sender shares the public key to outside the world who wants to send message to him privately.
  - Sender using private key signs the message and send to receiver
  - Receiver will use the senders publick key to verify the digital signature.
  - How Receiver will believe the public key send by the not the hacker ?
  - Digital signatiure itself will not verify the true identity of the sender and his public key.
  - The solution is Digital Certificate
  - Digital certificates are electronic credentials issued by trusted third party
  - It verifies the identity if the owner and also verifies the is the public key owned by the owner.
  -
  
  - After getting the Digital certifocate the receiver will not receive the public key instead
    Receiver will receives the Digital Certificate of the sender.
    
  - Sender will sends the following information to Trusted third party to get the Digital certificate.
      - 1.Certificates Owner name.
      - 2.Owner's public key and its expiration date.
      - 3.Certificate issuer name.
      - 4.Certificate issues's digital signature.
  
 Digital Certificate contains
 
    1.Senders ID information.
    2.Senders Public Key.
    3.CA Information .
    4.All the above (1,2,3) signed by the CA's Private Key .
    5.Ceritificate Validity Period.
  
With the above all the information CA Trusted Thrid party creates the Public Key Certificate.

  
  ```
