# RSA Algorithm

**Date:** 26-06-2026

---

# What is RSA?

RSA (Rivest–Shamir–Adleman) is one of the most widely used asymmetric encryption algorithms.

It uses a pair of keys:

* Public Key
* Private Key

RSA provides:

* Confidentiality
* Authentication
* Digital Signatures
* Secure Key Exchange

---

# Principle Behind RSA

RSA relies on the mathematical difficulty of factoring very large prime numbers.

Multiplying two large prime numbers is computationally easy.

Finding the original prime numbers from their product is extremely difficult.

This property forms the basis of RSA security.

---

# RSA Key Generation

## Step 1

Choose two prime numbers.

```text
p
q
```

Example:

```text
p = 17
q = 11
```

---

## Step 2

Calculate:

```text
n = p × q
```

Example:

```text
n = 17 × 11 = 187
```

The value of **n** is included in both the public and private keys.

---

## Step 3

Calculate Euler's Totient Function:

```text
φ(n) = (p − 1)(q − 1)
```

Example:

```text
φ(187) = 16 × 10 = 160
```

---

## Step 4

Choose **e** such that:

* 1 < e < φ(n)
* gcd(e, φ(n)) = 1

Example:

```text
e = 7
```

This becomes part of the public key.

---

## Step 5

Calculate **d**, the modular multiplicative inverse of **e**.

It satisfies:

```text
(d × e) mod φ(n) = 1
```

Example:

```text
d = 23
```

This becomes the private key.

---

# Public and Private Keys

**Public Key**

```text
(e, n)
```

Example:

```text
(7, 187)
```

**Private Key**

```text
(d, n)
```

Example:

```text
(23, 187)
```

---

# Encryption

To encrypt a message **M**:

```text
C = M^e mod n
```

Where:

* M = Plaintext
* C = Ciphertext
* e = Public exponent
* n = Modulus

Only the holder of the private key can decrypt the ciphertext.

---

# Decryption

To recover the original message:

```text
M = C^d mod n
```

Where:

* C = Ciphertext
* d = Private exponent
* n = Modulus

The original plaintext is obtained after decryption.

---

# Digital Signatures

RSA can also provide authentication.

The sender creates a signature using the private key.

The receiver verifies the signature using the sender's public key.

This ensures:

* Authenticity
* Integrity
* Non-repudiation

---

# Applications of RSA

* HTTPS
* SSL/TLS
* Secure Email
* VPNs
* Digital Certificates
* Digital Signatures
* Secure Key Exchange

---

# Advantages

* Strong security
* Public key distribution
* Supports encryption and digital signatures
* Widely trusted and implemented

---

# Limitations

* Slower than symmetric algorithms.
* Computationally expensive.
* Not suitable for encrypting large files directly.
* Often used only to exchange symmetric keys.

---

# Key Points for Revision

* RSA is an asymmetric algorithm.
* Uses a public/private key pair.
* Security depends on the difficulty of factoring large numbers.
* Public Key = (e, n)
* Private Key = (d, n)
* Encryption uses the public key.
* Decryption uses the private key.
* Digital signatures use the private key for signing and the public key for verification.
* RSA is commonly used for secure key exchange rather than bulk data encryption.
