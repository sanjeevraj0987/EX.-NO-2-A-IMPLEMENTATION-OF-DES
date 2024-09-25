# EX.-NO-2-A-IMPLEMENTATION-OF-DES

## AIM:
  To write a program to implement Data Encryption Standard (DES).

## ALGORITHM:

  STEP-1: Read the 64-bit plain text.
  
  STEP-2: Split it into two 32-bit blocks and store it in two different arrays.
  
  STEP-3: Perform XOR operation between these two arrays.
  
  STEP-4: The output obtained is stored as the second 32-bit sequence and the original second 32-bit sequence forms the first part.
  
  STEP-5: Thus the encrypted 64-bit cipher text is obtained in this way. Repeat the same process for the remaining plain text characters.
  
## PROGRAM:
```python
from Crypto.Cipher import DES
import binascii

print("DES: \n")
key = b'hello123'

def pad(text):
    while len(text) % 8 != 0:
        text += b'\x00'
    return text

des = DES.new(key, DES.MODE_ECB)

text = b'Data Encryption standard'
print("Original_Text: ",text)

pad_text = pad(text)

encrypted = des.encrypt(pad_text)

print("Encrypted text:", binascii.hexlify(encrypted))

decrypted = des.decrypt(encrypted)

print("Decrypted text:", decrypted.rstrip(b'\x00').decode())
```
## OUTPUT:

![image](https://github.com/VIKASHAR/EX.-NO-2-A-IMPLEMENTATION-OF-DES/assets/119405655/aef6b128-c42d-439b-825d-95500408f9cd)


## RESULT:

  Thus the data encryption standard algorithm had been implemented successfully.
