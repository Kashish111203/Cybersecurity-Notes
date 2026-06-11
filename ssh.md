# SSH (Secure Shell)

**Date-**10-06-2026

## Overview

SSH (Secure Shell) is a secure network protocol used to remotely access and manage systems over a network. It was designed as a secure replacement for Telnet and provides encrypted communication between a client and a server.

SSH is widely used in system administration, cloud computing, cybersecurity, and network management.

---

## Purpose of SSH

SSH allows administrators to:

* Access remote systems securely
* Execute commands remotely
* Transfer files securely
* Manage servers and network devices
* Automate administrative tasks

---

## How SSH Works

When an SSH connection is initiated:

1. The client connects to the server.
2. Cryptographic keys are exchanged.
3. A secure encrypted channel is established.
4. User authentication occurs.
5. Remote access is granted.

All communication is encrypted before transmission.

---

## Port Number

| Protocol | Port | Transport Protocol |
| -------- | ---- | ------------------ |
| SSH      | 22   | TCP                |

---

## Security Features

### Encryption

SSH encrypts all data exchanged between client and server.

This prevents attackers from reading intercepted traffic.

### Authentication

SSH supports multiple authentication methods:

* Password authentication
* Public key authentication
* Multi-factor authentication

### Integrity

SSH ensures that transmitted data cannot be modified without detection.

---

## SSH Authentication Methods

### Password Authentication

Users provide a username and password to access the remote system.

### Public Key Authentication

Uses a key pair:

#### Private Key

* Stored securely on the client
* Must remain secret

#### Public Key

* Stored on the server
* Used to verify identity

Public key authentication is generally more secure than passwords.

---

## Example Commands

Connect to a remote system:

```bash
ssh username@192.168.1.10
```

Example:

```bash
ssh admin@192.168.1.10
```

---

## File Transfer with SSH

### SCP

Securely copies files between systems.

Example:

```bash
scp file.txt user@192.168.1.10:/home/user
```

### SFTP

Provides secure file transfer functionality using SSH.

Benefits:

* Encrypted transfers
* Authentication support
* Secure file management

---

## Common Uses

SSH is commonly used for:

* Linux server administration
* Cloud server management
* Router and switch administration
* Secure remote troubleshooting
* Secure file transfers

---

## Advantages

* Strong encryption
* Secure authentication
* Data integrity protection
* Widely supported
* Industry standard for remote administration

---

## SSH vs Telnet

| Feature        | SSH    | Telnet |
| -------------- | ------ | ------ |
| Port           | 22     | 23     |
| Encryption     | Yes    | No     |
| Authentication | Strong | Basic  |
| Security       | High   | Low    |
| Recommended    | Yes    | No     |

---

## Key Points for Revision

* SSH stands for Secure Shell.
* Uses TCP Port 22.
* Encrypts all communication.
* Secure replacement for Telnet.
* Supports password and key-based authentication.
* SCP and SFTP use SSH for secure file transfers.
* Commonly used for remote administration.
