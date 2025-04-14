# Encryption and Hashing

Encryption is the process of scrambling your message.

To unscramble your message you require a key.

![[Pasted image 20231010120935.png|500]]

Encryption using Caesar Cipher Methods look like this -

![[Pasted image 20231010120946.png|500]]

To decrypt the cipher text -

![[Pasted image 20231010120959.png|500]]

Caesar Cipher is a very weak encryption method.

No matter where you store the encryption key there is a good chance that it may get exposed. This is where hashing comes in.

Hashing takes away the need for an encryption key for encryption.

![[Pasted image 20231010121045.png|500]]

We get the registration password from the user and then use the hash function to generate a hash for that password. This hash will then be stored in the password field in the database.

![[Pasted image 20231010121057.png|500]]

We get the login password from the user and then use the hash function to generate a hash value. We then compare this hash value with the hash value stored in the database. If a match is found we give the user access else we deny access to the user.

![[Pasted image 20231010121111.png|500]]