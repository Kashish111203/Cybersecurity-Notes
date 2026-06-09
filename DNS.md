# DNS Protocol Notes

**Date:** 07-06-2026

---

# What is DNS?

DNS (Domain Name System) translates human-readable domain names into IP addresses.

Example:

```text
google.com → 142.250.183.206
```

Without DNS, users would need to remember IP addresses instead of domain names.

---

# Why DNS is Important

* Makes websites easier to access
* Converts domain names into IP addresses
* Helps devices locate services on networks
* Supports internet communication

---

# DNS Resolution Process

1. User enters a domain name.
2. Browser sends a DNS query.
3. DNS resolver searches for the IP address.
4. IP address is returned.
5. Browser connects to the server.

Example:

```text
User
 ↓
DNS Resolver
 ↓
DNS Server
 ↓
IP Address Returned
 ↓
Website Opens
```

---

# DNS Record Types

## A Record

Maps a hostname to an IPv4 address.

Example:

```text
example.com → 192.168.1.10
```

---

## AAAA Record

Maps a hostname to an IPv6 address.

Example:

```text
example.com → 2001:db8::1
```

---

## CNAME Record

Creates an alias for another domain.

Example:

```text
www.example.com → example.com
```

---

## MX Record

Specifies the mail server for a domain.

Example:

```text
example.com → mail.example.com
```

---

## TXT Record

Stores text information.

Uses:

* SPF records
* Domain verification
* Security policies

---

# DNS Ports

| Protocol       | Port   |
| -------------- | ------ |
| DNS Queries    | UDP 53 |
| Zone Transfers | TCP 53 |

---

# DNS Caching

DNS responses can be stored temporarily.

Benefits:

* Faster lookups
* Reduced DNS traffic
* Improved performance

---

# Benefits of DNS

* Easy name resolution
* Scalable architecture
* Faster browsing through caching
* Supports internet services

---

# Exam Revision

* DNS = Domain Name System
* Converts names to IP addresses
* Port 53
* A = IPv4
* AAAA = IPv6
* MX = Mail Server
* CNAME = Alias


