## Elliptic Curve Cryptography

> - Elliptic Curve Cryptography (ECC) used in key exchange, encryption, and digital signature.

**Algorithm**

<p align=center>
  <img src="Figures/Fig-10.7.png" width="350" height="400" />
</p>                                                     

**Generate private key**

``openssl ecparam -name secp256k1 -genkey -noout -out PRa.pem``

**Extract public key**

``openssl ec -in private.pem -pubout -out PUa.pem``


> There are no tools for encrypting and decrypting! ECC doesn’t define these directly. Instead, ECC users use Diffie-Hellman (DH) key exchange to compute a shared secret, then communicate using that shared secret. This combination of ECC and DH is called ECDH.


**Generating sceret key**

``openssl pkeyutl -derive -inkey PRa.pem -peerkey PUb.pem -out SKa.bin``

**Comparing secret key**

``$ cmp SKa.bin SKb.bin``

**View Secret key**

``$ base64 SKa.bin``

**Encryption** (Using symmetric cipher)

``$ openssl enc -aes256 -base64 -k $(base64 SKa.bin) -e -in plain.txt -out cipher.txt``

**Decryption** (Using symmetric cipher)

``$ openssl enc -aes256 -base64 -k $(base64 SKb.bin) -d -in cipher.txt -out plain_again.txt``
