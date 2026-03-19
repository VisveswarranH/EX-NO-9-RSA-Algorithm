# EX-NO-9-RSA-Algorithm
## NAME:VISVESWARRAN HARIKRISHNAN
## REG :212224110063

## AIM:
To Implement RSA Encryption Algorithm in Cryptography

## Algorithm:


Step 1: Design of RSA Algorithm  
The RSA algorithm is based on the mathematical difficulty of factoring the product of two large prime numbers. It involves generating a public and private key pair, where the public key is used for encryption, and the private key is used for decryption.

Step 2: Implementation in Python or C 
This algorithm can be implemented in languages like Python or C by performing large integer calculations for key generation, encryption, and decryption, utilizing libraries for modular arithmetic if necessary.

Step 3: Algorithm Description  
1. Key Generation:
   - Select two large prime numbers \( p \) and \( q \).
   - Calculate \( n = p \times q \), which will be used as the modulus.
   - Compute the totient \( \phi(n) = (p - 1)(q - 1) \).
   - Choose a public exponent \( e \) such that \( e \) is coprime with \( \phi(n) \).
   - Compute the private key \( d \), which is the modular inverse of \( e \) mod \( \phi(n) \).

2. Encryption:
   - Convert the plaintext message \( M \) into a numerical form \( m \) (such that \( 0 \le m < n \)).
   - Compute the ciphertext \( c \) using the formula: \( c = m^e \mod n \).

3. Decryption:
   - Use the private key \( d \) to recover \( m \) from \( c \) using: \( m = c^d \mod n \).
   - Convert \( m \) back into the original message \( M \).

Step 4: Mathematical Representation  
- Encryption: \( E(m) = m^e \mod n \)
- Decryption: \( D(c) = c^d \mod n \)

Step 5: **Security Foundation  
The security of RSA relies on the difficulty of factoring large numbers; thus, choosing sufficiently large prime numbers for \( p \) and \( q \) is crucial for security.

## Program:
```
def gcd(a, b):
    while b != 0:
        a, b = b, a % b
    return a
def mod_inverse(e, phi):
    for d in range(1, phi):
        if (e * d) % phi == 1:
            return d
    return None

p = int(input("Enter prime number p: "))
q = int(input("Enter prime number q: "))

n = p * q

phi = (p - 1) * (q - 1)

e = int(input("Enter public key e (coprime with phi): "))

if gcd(e, phi) != 1:
    print("e is not coprime with phi. Choose another e.")
    exit()

d = mod_inverse(e, phi)

print("Public Key (e, n):", (e, n))
print("Private Key (d, n):", (d, n))

m = int(input("Enter message (number < n): "))
c = (m ** e) % n
print("Encrypted message:", c)

m_decrypted = (c ** d) % n
print("Decrypted message:", m_decrypted)
```



## Output:

<img width="1619" height="907" alt="image" src="https://github.com/user-attachments/assets/c5fe55e0-5b9b-4cf6-ba3c-d2210fc5f812" />

## Result:
 The program is executed successfully.
