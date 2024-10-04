# Work Guide: Block Ciphers

## Introduction to Linear Cryptanalysis
Linear cryptanalysis is a method used to analyze and break symmetric-key ciphers. It was introduced by Mitsuru Matsui in 1993 and is particularly effective against block ciphers like DES (Data Encryption Standard).

### Key Concepts
1. **Linear Approximation:** This involves finding linear equations that approximate the behavior of the cipher. These equations relate the plaintext, ciphertext, and key bits.
2. **Linear Hull:** A collection of linear approximations that can be combined to improve the success rate of the attack.
3. **Bias:** The difference between the probability of a linear approximation holding true and 0.5. A higher bias indicates a better approximation.

### Steps to Perform Linear Cryptanalysis
1. **Choose a Cipher:** Start with a simple block cipher, such as a Substitution-Permutation Network (SPN).
2. **Identify S-Boxes:** Analyze the substitution boxes (S-boxes) used in the cipher. These are crucial for finding linear approximations.
3. **Find Linear Approximations:** Determine linear equations that approximate the behavior of the S-boxes.
4. **Collect Data:** Gather a large number of plaintext-ciphertext pairs.
5. **Calculate Bias:** Use the collected data to calculate the bias of your linear approximations.
6. **Recover Key Bits:** Use the approximations with the highest bias to recover bits of the key.

### Tutorials and Papers:
- [A Tutorial on Linear and Differential Cryptanalysis](http://www.cs.bc.edu/~straubin/crypto2017/heys.pdf) by Howard M. Heys provides a detailed explanation of the techniques.
- [An Introduction to Linear Cryptanalysis](https://kevinliu.me/posts/linear-cryptanalysis/) by Kevin Liu offers a practical approach with examples.

### Videos:
- [Cryptanalysis - L8 Linear Cryptanalysis](https://www.youtube.com/watch?v=RE6xu5THyJA) by Maria Eichlseder.


## Data Encryption Standard (DES)

### Introduction
The Data Encryption Standard (DES) is a symmetric-key block cipher that was developed in the 1970s and became a standard for data encryption. Despite being replaced by more secure algorithms, understanding DES is fundamental for learning about modern cryptographic techniques.

### Key Concepts
- **Symmetric-Key Cryptography**: DES uses the same key for both encryption and decryption.
- **Block Cipher**: DES encrypts data in fixed-size blocks (64 bits).
- **Feistel Structure**: DES employs a Feistel network, which divides the data into two halves and processes them through multiple rounds of permutation and substitution.

### How DES Works
#### Initial Permutation (IP)
The initial permutation rearranges the bits of the plaintext to introduce diffusion.

#### Key Generation
1. **Key Schedule**: A 56-bit key is derived from the initial 64-bit key by discarding every 8th bit.
2. **Subkeys**: Sixteen 48-bit subkeys are generated for each of the 16 rounds of encryption.

#### Feistel Network
DES uses a 16-round Feistel structure:
1. **Expansion**: The right half of the data is expanded from 32 to 48 bits.
2. **Key Mixing**: The expanded data is XORed with the subkey.
3. **Substitution**: The result is passed through 8 S-boxes, each producing a 4-bit output.
4. **Permutation**: The 32-bit output from the S-boxes is permuted.
5. **Swap**: The left and right halves are swapped, except in the final round.

#### Final Permutation (FP)
The final permutation is the inverse of the initial permutation and produces the ciphertext.

### Recommended Resources
- **Tutorials and Papers**:
  - [Understanding DES Algorithm - CodingDrills](https://www.codingdrills.com/tutorial/cryptography-tutorial/des-algorithm) provides an in-depth look at the DES algorithm.
  - [Data Encryption Standard (DES) | Set 1 - GeeksforGeeks](https://www.geeksforgeeks.org/data-encryption-standard-des-set-1/) offers a comprehensive overview of DES.

- **Videos**:
  - [DES - Data Encryption Standard | Simplilearn](https://www.youtube.com/watch?v=S918rR4VdqQ) explains the DES algorithm with practical examples.
  - [Introduction to Data Encryption Standard (DES) | Neso Academy](https://www.youtube.com/watch?v=j53iXhTSi_s) provides a detailed introduction to DES.
 


## Advanced Encryption Standard (AES)

### Introduction
The Advanced Encryption Standard (AES) is a symmetric block cipher that has become the standard for data encryption. It was established by the National Institute of Standards and Technology (NIST) in 2001 and is widely used for securing sensitive data.

### Key Concepts
- **Symmetric-Key Cryptography**: AES uses the same key for both encryption and decryption.
- **Block Cipher**: AES encrypts data in fixed-size blocks of 128 bits.
- **Substitution-Permutation Network (SPN)**: AES uses a series of linked operations, including substitutions and permutations, to transform the plaintext into ciphertext.

### How AES Works
#### Key Sizes and Rounds
AES supports three key sizes:
- **AES-128**: 128-bit key, 10 rounds
- **AES-192**: 192-bit key, 12 rounds
- **AES-256**: 256-bit key, 14 rounds

#### Encryption Process
1. **Initial Round**:
   - **AddRoundKey**: XOR the plaintext with the initial round key.

2. **Main Rounds** (repeated for 9, 11, or 13 times depending on the key size):
   - **SubBytes**: Substitute each byte using a fixed S-box.
   - **ShiftRows**: Shift the rows of the state array cyclically.
   - **MixColumns**: Mix the columns of the state array (not in the final round).
   - **AddRoundKey**: XOR the state with a round key.

3. **Final Round**:
   - **SubBytes**
   - **ShiftRows**
   - **AddRoundKey**

#### Decryption Process
The decryption process of AES is essentially the reverse of the encryption process, using the inverse operations:
- **InvSubBytes**
- **InvShiftRows**
- **InvMixColumns**
- **AddRoundKey**

### Practical Applications
- **Data Security**: AES is used to secure data in various applications, including file encryption, secure communications, and data storage.
- **Wireless Security**: AES is a key component in securing wireless networks (e.g., WPA2).
- **Web Security**: AES is used in protocols like HTTPS to secure web traffic.

### Recommended Resources
- **Tutorials and Papers**:
  - [AES Encryption: Secure Data with Advanced Encryption Standard](https://www.simplilearn.com/tutorials/cryptography-tutorial/aes-encryption) by Simplilearn.
  - [Advanced Encryption Standard (AES) - GeeksforGeeks](https://www.geeksforgeeks.org/advanced-encryption-standard-aes/) provides a comprehensive overview.
 
- **Videos**:
  - [AES - Advanced Encryption Standard Algorithm In Cryptography | AES Explained](https://www.youtube.com/watch?v=Z_7aOkS8tOA) by Simplilearn.
  - [AES Explained (Advanced Encryption Standard) - Computerphile](https://www.youtube.com/watch?v=O4xNJsjtN6E) by Computerphile.

