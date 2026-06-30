# Diffie-Hellman Key Exchange

## Overview

Diffie-Hellman Key Exchange (DHKE) is a cryptographic algorithm that enables two parties to securely establish a shared secret key over an insecure network.

It is **not an encryption algorithm**. Instead, it is used to exchange a secret key, which can later be used with symmetric encryption algorithms like AES.

---

# Why is Diffie-Hellman Needed?

Symmetric encryption requires both users to possess the same secret key. Transmitting this key directly over the Internet is insecure because an attacker could intercept it.

Diffie-Hellman solves this problem by allowing both parties to independently calculate the same secret key without ever sending the key across the network.

---

# Public and Private Values

Both users agree on two **public values**:

* Prime Number (**P**)
* Generator (**G**)

Example:

```text
P = 23
G = 5
```

Each user also chooses a **private key**, which is kept secret.

Example:

```text
Alice: a = 6
Bob:   b = 15
```

---

# Key Exchange Process

### Step 1: Generate Public Keys

Alice calculates:

```text
A = G^a mod P
```

Bob calculates:

```text
B = G^b mod P
```

These public keys are exchanged.

---

### Step 2: Calculate Shared Secret

Alice computes:

```text
Shared Secret = B^a mod P
```

Bob computes:

```text
Shared Secret = A^b mod P
```

Both obtain the same secret key.

---

# Numerical Example

Public Values

```text
Prime (P) = 23
Generator (G) = 5
```

Private Keys

```text
Alice = 6
Bob   = 15
```

Public Keys

```text
Alice: 5^6 mod 23  = 8
Bob:   5^15 mod 23 = 19
```

### Key Exchange

```text
                     Public Network

        P = 23
        G = 5

+----------------+                  +----------------+
|     Alice      |                  |      Bob       |
|----------------|                  |----------------|
| Private = 6    |                  | Private = 15   |
| Public  = 8    | ---- 8 ------->  | Public  = 19   |
|                | <--- 19 -------- |                |
+----------------+                  +----------------+

Alice computes: 19^6 mod 23 = 2
Bob computes:    8^15 mod 23 = 2

Shared Secret Key = 2
```

Notice that the shared secret **2** is never transmitted across the network.

---

# Why is Diffie-Hellman Secure?

An attacker can see:

* Prime Number (P)
* Generator (G)
* Alice's Public Key
* Bob's Public Key

However, the attacker cannot efficiently determine the private keys because doing so requires solving the **Discrete Logarithm Problem**, which is computationally infeasible for large numbers.

---

# Advantages

* Secure key exchange over insecure networks
* Private keys are never transmitted
* Widely used in modern cryptographic protocols
* Enables secure symmetric encryption

---

# Limitations

* Does not encrypt data directly
* Does not provide authentication
* Vulnerable to Man-in-the-Middle (MITM) attacks if authentication is not used

---

# Applications

Diffie-Hellman is commonly used in:

* TLS/SSL (HTTPS)
* SSH
* IPSec
* VPNs
* Secure messaging applications

Modern systems often use **Elliptic Curve Diffie-Hellman (ECDH)** because it offers the same security with smaller key sizes.

