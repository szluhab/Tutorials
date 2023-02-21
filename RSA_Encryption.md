# **HOW TO:** RSA Encrption
## What is encryption?
---

## The code
---
Before we can start to generate keys and  encrypt data in python using RSA keys we need to make sure that we have the prerequisite packages installed. 

    $ pip install rsa

The RSA package we installed will allow us to generate private and public keys to use to encrypt our text using RSA. 

``` python
import rsa

publicKey, privateKey = rsa.newkeys(1024)

someText = "Hello"

#Encrypt the text
encrypted = rsa.encrypt(someText.encode(), publicKey)

#Decrypt the text
decrypted = rsa.decrypt(encrypted, privateKey).decode()
```

### **In the code above:**
- We import the rsa module.
 ``` python
 import rsa
 ```
- We created two keys, one public and one private. The rsa module will allways generate the public key first, then the private key. Note that an integer parameter is passed to the *newkeys()* method. This tells our code how complex we want the keys to be.
``` python
publicKey, privateKey = rsa.newkeys(1024)
```
- We defined some text to encrypt. This text could also have been from a .txt file or .csv file.
``` python
someText = "Hello"
```
- We encrypted the text. It is important to remember that we allways encrypt the text using the public key that we generated. We also encode our text into byte format with the *.encode()* method.
``` python
encrypted = rsa.encrypt(someText.encode(), publicKey)
```
- We decrypted our encrypted text. When decrypting, we can only use the private key that we generated. We use the *.decode()* method to convert the byte object into a string object. 
``` python
decrypted = rsa.decrypt(encrypted, privateKey).decode()
```

## Conclusion
---
This guide is just a simple explanation of how to encrypt or decrypt text with RSA. It can be expandedon by adding functionality to save and load the RSA keys, making the keys generated more usefull because of their persistance. 