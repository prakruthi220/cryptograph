# cryptograph
from Crypto.Cipher import DES
with open('plaintext.txt', 'rb') as f:
    plaintext = f.read()

key = b'c1823881'
cipher = DES.new(key, DES.MODE_ECB)
# (DES block size is 8 bytes)
plaintext += b' ' * (8 - len(plaintext) % 8)
ciphertext = cipher.encrypt(plaintext)
with open('encrypted_file.des', 'wb') as f:
    f.write(ciphertext)
