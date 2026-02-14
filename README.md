# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
``` python
def xor_crypt(data, key):
    key_len = len(key)
    result = []

    for i in range(len(data)):
        xor_char = ord(data[i]) ^ ord(key[i % key_len])
        result.append(xor_char)

    return result


# Main Program
msg = input("Enter message: ")
key = input("Enter key: ")

# Encrypt
encrypted = xor_crypt(msg, key)

print("Encrypted:", end=" ")
for byte in encrypted:
    print(f"{byte:02X}", end=" ")
print()

# Decrypt
# Convert numbers back to characters
decrypted = ""
for i in range(len(encrypted)):
    decrypted += chr(encrypted[i] ^ ord(key[i % len(key)]))

print("Decrypted:", decrypted)
```

## Output:
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/81959fda-f7a3-4f04-bf21-ee07b64133f7" />



## Result:
  The program is executed successfully

