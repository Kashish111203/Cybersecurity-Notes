# Hashing

## Overview

Hashing is the process of converting data of any size into a fixed-length value called a **hash** or **message digest**. Unlike encryption, hashing is a **one-way process**, meaning the original data cannot be recovered from the hash.

Hashing is widely used to verify data integrity, securely store passwords, and support digital signatures.

---

# How Hashing Works

A hashing algorithm takes an input (called a message or plaintext) and generates a unique hash value.

Example:

```text
Input:  Hello World

SHA-256

↓

Hash:
a591a6d40bf420404a011733cfb7b190...
```

Even a tiny change in the input produces a completely different hash.

Example:

```text
Hello World
↓

a591a6...

Hello world
↓

64ec88...
```

Notice that changing a single letter completely changes the hash.

---

# Characteristics of a Good Hash Function

A secure hashing algorithm should have the following properties:

* Produces a fixed-length output regardless of input size.
* Deterministic: the same input always produces the same hash.
* Fast to compute.
* One-way: the original input cannot be recovered from the hash.
* Avalanche Effect: a small change in the input results in a significantly different hash.
* Resistant to collisions.

---

# Common Hashing Algorithms

| Algorithm | Output Size | Status                           |
| --------- | ----------- | -------------------------------- |
| MD5       | 128 bits    | Not Secure                       |
| SHA-1     | 160 bits    | Deprecated                       |
| SHA-256   | 256 bits    | Secure                           |
| SHA-512   | 512 bits    | Secure                           |
| bcrypt    | Variable    | Password Hashing                 |
| scrypt    | Variable    | Password Hashing                 |
| Argon2    | Variable    | Recommended for Password Hashing |

---

# Applications of Hashing

Hashing is commonly used for:

* Password storage
* File integrity verification
* Digital signatures
* Blockchain
* Data integrity checks
* Message authentication

---

# Hash Collisions

## What is a Hash Collision?

A **hash collision** occurs when two different inputs produce the same hash value.

Example:

```text
Input A
      \
       > Same Hash
      /
Input B
```

Although collisions are mathematically possible because a fixed-length hash represents an unlimited number of possible inputs, a good hashing algorithm makes them extremely difficult to find.

---

## Why are Collisions Dangerous?

If an attacker can intentionally create a collision, they may be able to:

* Bypass integrity checks.
* Forge digital signatures.
* Replace files without detection.

This is one of the reasons why algorithms like **MD5** and **SHA-1** are no longer considered secure for many applications.

---

# Salting

## What is Salting?

A **salt** is a random value added to a password before hashing.

Instead of hashing only the password:

```text
password123
```

the system hashes:

```text
RandomSalt + password123
```

Example:

```text
Salt: X7g9K2

Password:
password123

Stored Value:
Hash(X7g9K2password123)
```

---

## Why is Salting Used?

Salting provides several security benefits:

* Prevents identical passwords from producing identical hashes.
* Protects against rainbow table attacks.
* Makes precomputed hash databases ineffective.
* Ensures every user's password hash is unique.

Each user should have a unique, randomly generated salt.

The salt is **not secret** and is usually stored alongside the password hash.

---

# Pepper

## What is Pepper?

A **pepper** is an additional secret value added before hashing, similar to a salt.

Unlike a salt, the pepper is **not stored in the database**. It is stored separately, such as in an application configuration file or a hardware security module (HSM).

Example:

```text
Pepper + Salt + Password

↓

Hash
```

---

## Why Use Pepper?

Pepper provides an additional layer of security.

If an attacker steals the password database, they still cannot recreate the hashes without knowing the secret pepper value.

Because the pepper is shared by the application and kept secret, compromising the database alone is not enough to perform successful offline attacks.

---

# Salt vs Pepper

| Feature              | Salt                    | Pepper                     |
| -------------------- | ----------------------- | -------------------------- |
| Random Value         | Yes                     | Can be fixed               |
| Secret               | No                      | Yes                        |
| Stored with Password | Yes                     | No                         |
| Unique for Each User | Yes                     | Usually No                 |
| Purpose              | Prevents rainbow tables | Adds an extra secret layer |

---

# Best Practices for Password Storage

Modern applications should:

* Never store passwords in plain text.
* Generate a unique random salt for every password.
* Use a slow password hashing algorithm such as **Argon2**, **bcrypt**, or **scrypt**.
* Optionally use a pepper for additional protection.
* Avoid outdated algorithms like **MD5** and **SHA-1** for password storage.

---

# Key Points for Revision

* Hashing is a **one-way process**.
* The same input always produces the same hash.
* A small input change causes a completely different output (Avalanche Effect).
* Hash collisions occur when two different inputs generate the same hash.
* Salting adds a unique random value to each password before hashing.
* Pepper is a secret value stored separately from the password database.
* Modern password hashing algorithms include **Argon2**, **bcrypt**, and **scrypt**.
* Hashing is used for password storage, integrity verification, and digital signatures.
