# IPv4 Addressing Notes

**Date:** 05-06-2026

---

# What is IPv4?

IPv4 (Internet Protocol Version 4) is used to uniquely identify devices on a network.

Every device communicating using IPv4 requires a unique IP address.

Example:

```text
192.168.1.165
```

---

# IPv4 Address Structure

IPv4 addresses contain:

* 32 bits total
* Divided into 4 groups
* Each group is called an octet
* Each octet contains 8 bits

Example:

```text
192.168.1.165
```

Binary form:

```text
11000000.10101000.00000001.10100101
```

Therefore:

```text
4 Octets = 32 Bits
```

---

# Octets

Each section of an IPv4 address is called an octet.

Example:

```text
192 . 168 . 1 . 165
 ↑     ↑    ↑    ↑
Octet Octet Octet Octet
```

Maximum value of an octet:

```text
255
```

---

# Subnet Mask

Subnet masks work together with IP addresses.

Example:

```text
IP Address:

192.168.1.165

Subnet Mask:

255.255.255.0
```

Purpose:

* Determines local subnet
* Helps identify local vs remote networks

Subnet masks are generally used locally by the device.

---

# Default Gateway

Default gateway allows communication outside the local network.

Example:

```text
IP Address:

192.168.1.165

Gateway:

192.168.1.1
```

Without gateway:

* Communication stays local

With gateway:

* Device can reach external networks

---

# Loopback Address

Used to test local networking stack.

Common Example:

```text
127.0.0.1
```

Loopback Range:

```text
127.0.0.1

to

127.255.255.254
```

Used for:

* Local testing
* Troubleshooting

---

# Reserved Addresses

Certain IPv4 ranges are reserved.

Reserved Range:

```text
240.0.0.1

to

254.255.255.254
```

These addresses are not normally assigned to devices.

---

# Virtual IP Addresses (VIP)

VIP = Virtual IP Address

Characteristics:

* Not tied to physical network adapter
* Used internally
* Can be assigned to virtual machines or services

Used for:

* Virtual machines
* Routers
* High availability systems

---

# Public IP Addresses

Characteristics:

* Reachable through internet
* Must be globally unique

Used for:

* Internet communication

---

# Private IP Addresses

Used inside local networks.

Ranges:

Class A:

```text
10.0.0.0 – 10.255.255.255
```

Class B:

```text
172.16.0.0 – 172.31.255.255
```

Class C:

```text
192.168.0.0 – 192.168.255.255
```

Private addresses are not directly reachable from internet.

---

# Automatic Addressing (APIPA)

If automatic configuration fails, device may assign itself an address.

Range:

```text
169.254.0.0

to

169.254.255.255
```

Usually indicates:

* DHCP unavailable
* Address assignment failure

---

# IPv4 and OSI Model

IPv4 operates at:

```text
OSI Layer 3
```

Layer Name:

```text
Network Layer
```

---

# Quick Revision

* IPv4 = 32 bits
* 4 octets
* Subnet mask identifies subnet
* Gateway communicates outside network
* Loopback = 127.x.x.x
* APIPA = 169.254.x.x
* IPv4 works at Layer 3
* Private IPs are not internet routable

