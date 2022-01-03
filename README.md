# Secret-Key-Encryption-lab

Task 2: Encryption using Different Ciphers and Modes

We used the provided ciphertext. Below is the decrypted result in plaintext.
![image](https://user-images.githubusercontent.com/93581168/147961895-714575b5-c1db-4626-8794-0d67cf295bb8.png)
Three different types of encryption below.
![image](https://user-images.githubusercontent.com/93581168/147962088-b0209a2a-bb02-4888-8ddb-4e17a520d77f.png)
Task 3: Encryption Mode – ECB vs. CBC

Image encryption using ECB and CBC
![image](https://user-images.githubusercontent.com/93581168/147962054-2466db67-e5ab-4686-ac35-32d1c2cbefc4.png)
Making encrypted file viewable as image.
![image](https://user-images.githubusercontent.com/93581168/147962191-72e6dc34-73ba-44ed-ac87-423ad0556013.png)
Viewing ECB encrypted image.
![image](https://user-images.githubusercontent.com/93581168/147962226-6184baf5-26a1-4c46-b29c-5362c5eec0e2.png)
Viewing CBC encrypted image.![image](https://user-images.githubusercontent.com/93581168/147962254-f0528c42-a73e-46cf-9e27-59b8a1e88fc5.png)
Viewing ECB encrypted image. Can make out some of the original image letters.
![image](https://user-images.githubusercontent.com/93581168/147962283-16153fa7-62f3-402e-85a2-ac06bf8da12f.png)

Viewing CBC encrypted file. Cannot make out any of the original image’s letters.
2. Yes, using the ECB encryption it is very easy to make out the shapes of the encrypted image. When using the CBC encryption I cannot see any relationship between the actual image and the encrypted image. When I ran the above encryption again with a newly chosen image, the results were the same. With ECB, I could make out some of the original image in the encrypted image. With CBC, I was unable to recognize any of the original image in the encrypted image.

Task 4: Padding

1. I began by creating a text file of size 27 bytes. After encrypting the 27 byte file I got the following results with different encryption:
ECB - file size became 32 bytes. Padding was used. CBC - file size became 32 bytes. Padding was used. CFB - files size remained 27 bytes. No padding.
OFB - file size remained 27 bytes. No padding.

Conclusion is that CFB and OFB do not use padding because they are stream ciphers and therefore the plaintext message does not need to be a multiple of the block-size.
 
Creating three files size 5, 10, 16 bytes

Image of encrypted 5 bytes file, size is 16 bytes.
![image](https://user-images.githubusercontent.com/93581168/147962337-c054d951-0fec-4b39-8bb5-8607c36743fb.png)
Image of encrypted 10 bytes file, size is 16 bytes.
![image](https://user-images.githubusercontent.com/93581168/147962352-41ad890d-43c2-4c4b-9cee-46a104321005.png)
Image of encrypted 16 bytes file, size is 32 bytes.
![image](https://user-images.githubusercontent.com/93581168/147962381-6ea49c36-451d-422f-9499-840281bf4e7a.png)
Hex Dump results for finding how each file was padded
![image](https://user-images.githubusercontent.com/93581168/147962396-104ae178-18dd-49d2-967f-df8a2eae13e2.png)
#Task 5: Error Propagation – Corrupted Cipher Text
