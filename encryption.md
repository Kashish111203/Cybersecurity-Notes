# Encryption Fundamentals

**Date:** 27-06-2026

---

# What is Encryption?

Encryption is the process of converting readable data (plaintext) into an unreadable format (ciphertext) so that only authorized users can access the original information.

The primary objectives of encryption are:

* Confidentiality
* Data Security
* Privacy
* Protection against unauthorized access

The reverse process of converting ciphertext back into plaintext is known as **decryption**.

---

# Basic Terminology

**Plaintext**

The original readable message.

Example:

```text
HELLO
```

**Ciphertext**

The encrypted and unreadable form of the plaintext.

Example:

```text
X7A91#PQ
```

**Encryption Algorithm**

A mathematical procedure used to convert plaintext into ciphertext.

**Key**

A value used by the encryption algorithm to encrypt and decrypt data.

---

# Types of Encryption

Encryption techniques are broadly classified into two categories:

1. Symmetric Encryption
2. Asymmetric Encryption

---

# Symmetric Encryption

## Definition

Symmetric encryption uses **one single key** for both encryption and decryption.

The sender and receiver must possess the same secret key before communication begins.

### Working

1. Sender encrypts plaintext using the secret key.
2. Ciphertext is transmitted.
3. Receiver decrypts the ciphertext using the same secret key.

Since both parties use the same key, it must remain confidential.

---

## Advantages

* Very fast
* Efficient for large amounts of data
* Requires less computational power

---

## Disadvantages

* Secure key distribution is difficult.
* If the key is compromised, all encrypted communication becomes insecure.
* Poor scalability in large organizations because each pair of users requires a unique shared key.

---

## Common Symmetric Algorithms

* AES (Advanced Encryption Standard)
* DES (Data Encryption Standard)
* Triple DES (3DES)
* Blowfish
* RC4 (legacy)

---

# Asymmetric Encryption

## Definition

Asymmetric encryption uses **two different but mathematically related keys**:

* Public Key
* Private Key

The public key can be shared openly, while the private key must always remain secret.

A message encrypted with one key can only be decrypted using its corresponding paired key.

---

## Advantages

* Solves the key distribution problem.
* Enables secure communication over insecure networks.
* Supports digital signatures and authentication.

---

## Disadvantages

* Slower than symmetric encryption.
* Requires more computational resources.
* Not suitable for encrypting very large amounts of data directly.

---

# Public Key

The public key is distributed openly and can be shared with anyone.

Its purpose is to:

* Encrypt messages
* Verify digital signatures

---

# Private Key

The private key is kept secret by its owner.

Its purpose is to:

* Decrypt encrypted messages
* Create digital signatures

---

# Four Possible Cases in Asymmetric Encryption

## Case 1

### Sender encrypts using Receiver's Public Key

### Receiver decrypts using Receiver's Private Key

**Purpose**

Confidentiality

Only the receiver possesses the private key required for decryption.

This is the most common use of public key cryptography.

---

## Case 2

### Sender encrypts using Sender's Private Key

### Receiver decrypts using Sender's Public Key

**Purpose**

Authentication and Digital Signature

Since anyone can use the sender's public key to decrypt the message, confidentiality is **not** achieved.

Instead, this proves that the message was created by the sender because only the sender possesses the private key.

---

## Case 3

### Encrypt using Receiver's Public Key

### Decrypt using Sender's Public Key

This combination does **not** work because the keys do not belong to the same key pair.

Decryption is impossible.

---

## Case 4

### Encrypt using Sender's Private Key

### Decrypt using Receiver's Private Key

This combination is also impossible because the encryption and decryption keys belong to different key pairs.

---

# Symmetric vs Asymmetric Encryption

| Feature          | Symmetric              | Asymmetric                                       |
| ---------------- | ---------------------- | ------------------------------------------------ |
| Number of Keys   | One                    | Two                                              |
| Speed            | Fast                   | Slow                                             |
| Security         | Depends on key secrecy | More secure key distribution                     |
| Key Distribution | Difficult              | Easy                                             |
| Used For         | Bulk data encryption   | Key exchange, authentication, digital signatures |

---

# Where They Are Used Together

Modern protocols such as HTTPS use **both** symmetric and asymmetric encryption.

1. Asymmetric encryption securely exchanges a symmetric session key.
2. Symmetric encryption is then used for the actual communication because it is much faster.

This approach combines the security of asymmetric encryption with the efficiency of symmetric encryption.

---

# Key Points for Revision

* Encryption converts plaintext into ciphertext.
* Decryption converts ciphertext back into plaintext.
* Symmetric encryption uses one shared key.
* Asymmetric encryption uses a public/private key pair.
* Public key can be shared openly.
* Private key must remain secret.
* Public Key → Encrypt → Private Key → Decrypt = Confidentiality.
* Private Key → Encrypt/Sign → Public Key → Verify = Authentication and Digital Signature.
* Mixed key pairs cannot decrypt each other's data.
