# DHCP Protocol Notes

**Date:** 08-06-2026

---

# What is DHCP?

DHCP (Dynamic Host Configuration Protocol) automatically assigns network settings to devices.

Instead of manually configuring:

* IP Address
* Subnet Mask
* Default Gateway
* DNS Server

DHCP performs these tasks automatically.

---

# Why DHCP is Important

* Saves administration time
* Reduces human errors
* Simplifies network management
* Automates address assignment

---

# Information Provided by DHCP

DHCP can provide:

* IP Address
* Subnet Mask
* Default Gateway
* DNS Server
* Lease Duration

---

# DHCP Process (DORA)

## Discover

Client searches for DHCP servers.

---

## Offer

Server offers an available IP address.

---

## Request

Client requests the offered address.

---

## Acknowledge

Server confirms the assignment.

---

# DORA Sequence

```text
Client
   |
Discover
   ↓
Server
   |
Offer
   ↓
Client
   |
Request
   ↓
Server
   |
Acknowledge
   ↓
IP Assigned
```

---

# DHCP Ports

| Device      | Port   |
| ----------- | ------ |
| DHCP Server | UDP 67 |
| DHCP Client | UDP 68 |

---

# DHCP Lease

A lease is the time period for which an IP address is assigned.

When the lease expires:

* Client attempts renewal
* Server may renew or assign another address

---

# APIPA

Automatic Private IP Addressing occurs when DHCP fails.

Range:

```text
169.254.0.0 - 169.254.255.255
```

Indicates:

* DHCP server unavailable
* Network configuration issue

---

# Advantages of DHCP

* Automatic configuration
* Centralized management
* Efficient IP utilization
* Reduced administrative workload

---

# DHCP vs Static Addressing

| DHCP               | Static IP                |
| ------------------ | ------------------------ |
| Automatic          | Manual                   |
| Easier to manage   | More administrative work |
| Dynamic assignment | Fixed assignment         |

---

# Exam Revision

* DHCP = Dynamic Host Configuration Protocol
* Assigns IP configuration automatically
* Uses UDP Ports 67 and 68
* Uses DORA Process
* APIPA = 169.254.x.x

