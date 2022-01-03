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
Created a text file greater than 1000 bytes in size. The file is essentially a repeat of NazimZerrouki and GregGertsen (our full names) until we reached or exceeded 1000 bytes. We then encrypted the file using AES 128 bit block ciphers using ECB, CBC, CFB, and OFB. The key and IV that were used was ‘00112233445566778899aabbccddeeff’ and ‘aabbccddeeff998877665544332211’ unless stated otherwise. The files prior to corrupting the 55th bit for ECB, CBC, CFB, and OFB respectively which are shown below:

![image](https://user-images.githubusercontent.com/93581168/147962539-e6cd4669-c311-47f5-a7a4-2e6899cf59ee.png)

![image](https://user-images.githubusercontent.com/93581168/147962549-cfdc21c4-4025-4977-b436-e9c3ac0de611.png)

![image](https://user-images.githubusercontent.com/93581168/147962567-7592c760-11a8-4b0e-9290-a3bae7f6a8dd.png)

![image](https://user-images.githubusercontent.com/93581168/147962580-43dd418a-6b4a-474b-a0e3-cbb97f06ee4c.png)

Corrupted encryption by changing 1 bit of the encrypted file for each type of encryption are shown below in the same order.

![image](https://user-images.githubusercontent.com/93581168/147962606-1235d225-9882-4801-ae08-2b8e346cd6f3.png)

Observation:

![image](https://user-images.githubusercontent.com/93581168/147962631-20ed36a7-0b9f-4fb7-a158-de73e15b468c.png)

Using ECB to decrypt the corrupted file, we noticed that the first 16 bytes (64 bits) were corrupted while the rest of the bits were completely unaffected.

![image](https://user-images.githubusercontent.com/93581168/147962668-a6e61724-ae3a-42e0-9075-c76e262a9a96.png)

Observation.

![image](https://user-images.githubusercontent.com/93581168/147962718-bd2914e1-1175-46fc-96ac-9a56001df239.png)

For CBC, after decrypting the corrupted file, we noticed that the majority of the first 23 bytes 

![image](https://user-images.githubusercontent.com/93581168/147962743-5d4062ae-b7bd-408f-a6cd-8c5fd5e4fc9e.png)


(roughly first 72 bits) were corrupted while the rest of the bits remained unaffected.

Observation:

![image](https://user-images.githubusercontent.com/93581168/147962789-ff15eff2-a076-44ca-945e-34bf71567a06.png)


When decrypting using CFB, we noticed that the 7th byte was corrupted and bytes 17-21 and bytes 23-32 were corrupted as well. The remaining file was left completely unaffected.

![image](https://user-images.githubusercontent.com/93581168/147962954-1d5e73d9-2337-4bbf-8040-80934a5399e2.png)

Observation:

![image](https://user-images.githubusercontent.com/93581168/147963058-e1ec7dfa-dd14-4a3d-957a-5c2ce3d9daba.png)

When decrypting using OFB, we noticed that only the 7th byte was corrupted while the rest of the bytes remained intact.
Task 6: Initial Vector (IV) and Common Mistakes
Task 6.1. IV Experiment

Using the same IV twice on the same plaintext file resulted in and identical output for the encryption.

![image](https://user-images.githubusercontent.com/93581168/147963257-704d41b9-a7b9-46e8-8bc9-f7b9a41c9310.png)

With different IVs the encryption results were completely different.

![image](https://user-images.githubusercontent.com/93581168/147963407-61306b4a-dea6-41c8-ac43-b640db1b2ac8.png)

The IV needs to be unique because if we are using the same plaintext more than once, not having a unique IV each time will result in an identical ciphertext and a pattern will start to emerge if there is an adversary observing our encryption.

Task 6.2. Common Mistake: Use the Same IV

When reusing OFB and same IV for encryption, even if our two plaintext messages to be encrypted are not identical there patterns will start to emerge and the algorithm will become deterministic. IN the case of P1> C1, P2>C2 there are some repeats in the ciphertext between C1 and C2, this can be used to crack the encryption. By looking at the two ciphertext it looks like maybe both plaintext messages end with an ‘!’ mark.

When using CFB the attacker can only know the first block of the message. Task 6.3. Common Mistake: Use a Predictable IV
If you know that the plaintext is either ‘yes’ or ‘no’ and you need to guess which one it is from cipher text and you can predict the IV. Then it is possible to verify your guess by submitting either ‘yes’ or ‘no’ with a known IV.

Task 7: Programming using the Crypto Library

For task 7 we wrote a program in Python using the Pycrypto library formaking a dictionary attack on the AES-128-CBC encryption. The program works and I have demonstrated this below with screenshots. Basically,  when given a ciphertext, message, and IV.  It will run through a word list + padding them with #s to be 16 bytes long, and when it outputs a match to the desired ciphertext then program ends and then displays the key that generated the result. The only issue was that perhaps due to the different implementation of the encryption library as compared to Openssl, I was unable to generate the same key that was given to us in the lab.
Therefore, I just generated a new ciphertext as the target and ran the program until it matched it. In this regard it worked fine. Please see below images

Program and output after finding the key, word was ‘backpack’ (‘backpack########’). This image shows top half of program


![image](https://user-images.githubusercontent.com/93581168/147963444-cf01af06-0c27-4554-9802-11d52ded20a2.png)

This image shows remaining bottom half of program. And demonstrates that we were able to run a successful dictionary attack on AES-128-CBC encryption when given the IV, message, and ciphertext.

![image](https://user-images.githubusercontent.com/93581168/147963472-2fd11b2c-11bf-45f4-b95f-daca0d44f1c4.png)


