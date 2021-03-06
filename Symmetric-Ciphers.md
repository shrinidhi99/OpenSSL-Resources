## Symmetric Ciphers (Encryption and Decryption)

**A Simplified Model of Symmetric Encryption**        

<p align=center>
<img src="Figures/Fig2.png" width="400" height="150" />
</p>

### Base64

**Encryption**

``openssl enc -base64 -in number.txt -out cipher.txt``

**View cipher text**

``cat cipher.txt``

``xxd cipher.txt``

**Decryption**

``openssl enc -base64 -d -in cipher.txt -out number1.txt``

**Verification**

``cmp number.txt number1.txt``

### Data Encryption Standard (DES)

**Encryption and Decryption**

<p align=center>
<img src="Figures/DES-1.png" width="250" height="400" />
</p>

**2-DES**

<p align=center>
<img src="Figures/DES-2.png" width="300" height="150" />
</p>

**3-DES**

<p align=center>
<img src="Figures/DES-3.png" width="350" height="150" />
</p>

**Encryption**

``openssl des3 -in file.txt -out file.des3``

**View cipher text**

``cat file.des3``

``xxd file.des3``

**Decryption**

``openssl des3 -d -in file.des3 -out filed.txt``

**Verification**

``cmp file.txt filed.txt``

### Advanced Encryption Standard (AES)

**Encryption and Decryption**

<p align=center>
<img src="Figures/AES-3.png" width="300" height="400" />
</p>

**Variants of AES**

<p align=center>
<img src="Figures/AES-2.png" width="300" height="90" />
</p>

**Encryption** (Interactive)

``openssl enc -aes-256-cbc -in plain.txt -out encrypted.bin``

**Encryption** (non-interactive)

``openssl enc -aes-256-cbc -in plain.txt -out encrypted.bin -pass pass:hello``

``sudo openssl enc -aes-256-cbc -salt -in plain.txt -out encrypted.bin -k PASS -a`` (Base64 format output)

**Decryption** (interactive)

``openssl enc -d -aes-256-cbc -in encrypted.bin -out decrypt.txt``

**Decryption** (non-interactive)

``openssl enc -d -aes-256-cbc -in encrypted.bin -out decrypt.txt -pass pass:hello``

``openssl enc -aes-256-cbc -d -in encrypted.bin -k PASS -a``

**View cipertext**

``cat encrypted.bin`` (for Base64 format)

``xxd encrypted.bin`` (for other format)

## Reference

[openssl enc](https://www.openssl.org/docs/manmaster/man1/enc.html)

