# IPv6 Addressing Notes

**Date:** 06-06-2026
---

# What is IPv6?

IPv6 (Internet Protocol Version 6) is the newer version of IP addressing designed to replace IPv4.

Reasons for IPv6:

* IPv4 address exhaustion
* Larger address space
* Better routing efficiency
* Improved auto configuration

---

# IPv6 Address Format

IPv6 Address:

2001:0db8:85a3:0000:0000:8a2e:0370:7334

Characteristics:

* 128 bits
* 8 groups
* Hexadecimal numbers
* Groups separated using :

---

# Shortening IPv6 Addresses

Rules:

Remove leading zeros:

2001:0db8:0000:0001

↓

2001:db8:0:1

Consecutive zeros:

2001:db8:0:0:0:0:0:1

↓

2001:db8::1

---

# Types of IPv6 Addresses

## Global Unicast

* Public IPv6 addresses
* Internet routable

## Link Local

Range:

fe80::/10

Used for:

* Local network communication

## Loopback

::1

Equivalent of:

127.0.0.1

## Multicast

One-to-many communication

No broadcast exists in IPv6.

---

# IPv6 Advantages

* Larger address space
* Auto configuration
* Better efficiency
* No NAT required

---

# Revision

* IPv6 = 128 bits
* Uses hexadecimal
* :: compresses zeros
* No broadcast
* Loopback = ::1
