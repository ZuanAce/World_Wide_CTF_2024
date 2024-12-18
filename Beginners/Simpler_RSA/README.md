# Simpler RSA ✅

## Challenge Description
> ![image](https://github.com/user-attachments/assets/300a4d0f-6a25-460e-a6b0-05d391d60ff8)

----

## Challenge Overview
 We were given a ciphertext and two large primes, `p` and `q`, along with a Python script that implements an encryption scheme similar to RSA. However, instead of using a public exponent $e$, the script uses `p` as the exponent and `q` as the modulus. Our goal was to decrypt the ciphertext and recover the flag.

 ----

## Encryption Formula
The encryption used the formula:<br>
$c = flag^p mod q$<br>
Where p is the exponent, q is the modulus, and flag is the secret message.

----

## Solution Approach
1. **Modular Inverse**: To decrypt, we need the modular inverse of p modulo $𝑞−1$, because of Euler's theorem. This inverse allows us to reverse the exponentiation.
2. **Decryption**: Once we have the modular inverse 𝑑 of p, the flag can be recovered by: $flag = c^d mod q$
3. **Implementation**: Using Python’s `pow` function, we compute the modular inverse and decrypt the ciphertext.
4. **Execution**: Running the code gives us the flag.

----

## Python Code:
```python
from Crypto.Util.number import long_to_bytes

# Given values (from the challenge)
p = <given_p>
q = <given_q>
c = <given_c>

# Step 1: Find modular inverse of p modulo (q-1)
d = pow(p, -1, q - 1)

# Step 2: Decrypt the ciphertext
m = pow(c, d, q)

# Step 3: Convert to bytes and print the flag
flag = long_to_bytes(m)
print(flag.decode())
```
   
## Flag: 
wwf{ju57_u53_l1br4r135}



   



