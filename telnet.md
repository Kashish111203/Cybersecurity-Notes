# Telnet Protocol

**Date-**10-06-2026

## Overview

Telnet (Telecommunication Network) is a network protocol that allows a user to remotely access and manage another device over a network. It provides a command-line interface to a remote system, enabling administrators to execute commands and perform management tasks from a distance.

Telnet was one of the earliest protocols developed for remote administration and is still found on some legacy systems and networking devices.

---

## Purpose of Telnet

The primary purpose of Telnet is to establish a remote terminal session between a client and a server.

Using Telnet, administrators can:

* Access remote devices
* Configure network equipment
* Troubleshoot systems
* Execute commands remotely

---

## How Telnet Works

When a user initiates a Telnet connection, a TCP session is established between the client and the remote device.

After successful connection:

1. The user is prompted for credentials.
2. The remote system verifies the credentials.
3. A command-line session is established.
4. Commands can be executed remotely.

The communication occurs in plain text.

---

## Port Number

| Protocol | Port | Transport Protocol |
| -------- | ---- | ------------------ |
| Telnet   | 23   | TCP                |

---

## Security Issues

One of the biggest disadvantages of Telnet is the lack of encryption.

All information transmitted through a Telnet session is sent in plain text, including:

* Usernames
* Passwords
* Commands
* Responses

An attacker monitoring network traffic can easily capture this information.

Because of this weakness, Telnet is considered insecure and is rarely used in modern production environments.

---

## Common Uses

Historically, Telnet was used for:

* Server administration
* Router configuration
* Switch configuration
* Remote troubleshooting

Today it is mostly used for:

* Testing connectivity to specific ports
* Legacy device administration
* Learning networking concepts

---

## Example Command

```bash
telnet 192.168.1.10
```

This attempts to establish a Telnet session with the target host.

---

## Advantages

* Easy to use
* Lightweight
* Supported by many legacy devices
* Useful for testing network services

---

## Disadvantages

* No encryption
* No secure authentication
* Vulnerable to packet sniffing
* Not suitable for sensitive environments

---

## Key Points for Revision

* Telnet stands for Telecommunication Network.
* Uses TCP Port 23.
* Provides remote command-line access.
* Sends data in plain text.
* Considered insecure.
* Mostly replaced by SSH.
