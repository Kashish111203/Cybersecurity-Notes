# ARP Protocol (Address Resolution Protocol)

**Date:** 09-06-2026

## Overview

ARP (Address Resolution Protocol) is a network protocol used to discover the MAC address associated with an IPv4 address on a local network. Since devices use IP addresses for logical communication and MAC addresses for physical delivery on a LAN, ARP acts as a bridge between Layer 3 (Network Layer) and Layer 2 (Data Link Layer).

Whenever a device wants to communicate with another device on the same network, it must know the destination device's MAC address. If it only knows the IP address, ARP is used to find the corresponding MAC address.

---

## Why ARP is Necessary

Consider a computer that wants to send data to another device with the IP address `192.168.1.10`.

The computer can identify the destination using the IP address, but Ethernet communication requires a MAC address to deliver the frame across the local network. ARP allows the sender to discover the MAC address associated with that IP address before communication begins.

Without ARP, devices would not be able to translate IPv4 addresses into MAC addresses and local network communication would not be possible.

---

## How ARP Works

When a device needs the MAC address corresponding to an IP address, it first checks its ARP cache. The ARP cache is a temporary table that stores previously learned IP-to-MAC mappings.

If the required entry is not found in the cache, the device sends an ARP Request. This request is broadcast to every device on the local network and essentially asks:

"Who has this IP address?"

Every device on the network receives the request, but only the device whose IP address matches the requested address responds.

The matching device sends an ARP Reply containing its MAC address. The sender stores this information in its ARP cache and uses it to send Ethernet frames to the destination.

---

## ARP Request

An ARP Request is a broadcast message sent to all devices on the local network.

The request contains:

* Sender IP address
* Sender MAC address
* Target IP address
* Unknown target MAC address

Because the sender does not yet know the destination MAC address, the Ethernet frame is sent to the broadcast MAC address:

`FF:FF:FF:FF:FF:FF`

Every device receives the request, but only the correct device responds.

---

## ARP Reply

An ARP Reply is a unicast message sent directly to the requesting device.

The reply includes:

* Sender IP address
* Sender MAC address

After receiving the reply, the requesting device updates its ARP cache and begins normal communication.

Unlike ARP Requests, ARP Replies are not broadcast across the network.

---

## ARP Cache

To reduce network traffic, devices store ARP information in a local cache.

The ARP cache contains mappings between IP addresses and MAC addresses. When a device needs to communicate with a known host, it can use the cached information instead of generating another ARP Request.

ARP cache entries eventually expire and are removed automatically. If communication is needed again after expiration, a new ARP Request is generated.

---

## Viewing the ARP Cache

On Windows systems, the ARP cache can be viewed using:

```bash
arp -a
```

On Linux systems:

```bash
arp -a
```

or

```bash
ip neigh
```

These commands display the current IP-to-MAC address mappings stored by the operating system.

---

## ARP and the OSI Model

ARP operates between the Data Link Layer and the Network Layer.

Although ARP works with IP addresses, it does not technically belong to the Network Layer. Its purpose is to translate Layer 3 addresses into Layer 2 addresses so that communication can occur on a local network.

For this reason, ARP is often described as operating between Layer 2 and Layer 3.

---

## Gratuitous ARP

A Gratuitous ARP occurs when a device sends an ARP message for its own IP address.

This can be used to:

* Detect duplicate IP addresses
* Update ARP tables on other devices
* Support failover and redundancy systems

Network administrators often encounter Gratuitous ARP in high-availability environments.

---

## ARP Spoofing (ARP Poisoning)

ARP was designed without authentication, which makes it vulnerable to attacks.

In an ARP Spoofing attack, an attacker sends forged ARP Replies containing false MAC address information. As a result, victims update their ARP caches with incorrect entries.

This can allow an attacker to:

* Intercept network traffic
* Perform Man-in-the-Middle attacks
* Capture sensitive information
* Modify network communications

ARP Spoofing is one of the most common attacks discussed in network security and cybersecurity courses.

---

## Limitations of ARP

ARP has several limitations:

* It only works with IPv4.
* It functions only on local networks.
* ARP broadcasts can increase network traffic.
* It provides no authentication mechanism.
* It cannot operate across routers.

Because of these limitations, IPv6 does not use ARP.

---

## ARP in IPv6

IPv6 replaces ARP with the Neighbor Discovery Protocol (NDP).

NDP performs similar functions, including:

* Address resolution
* Neighbor discovery
* Router discovery

NDP is more efficient and provides additional functionality compared to ARP.

---

## Key Points for Revision

* ARP stands for Address Resolution Protocol.
* ARP maps IPv4 addresses to MAC addresses.
* ARP Requests are broadcast messages.
* ARP Replies are unicast messages.
* Devices store mappings in an ARP cache.
* ARP operates between Layer 2 and Layer 3.
* IPv6 uses Neighbor Discovery Protocol (NDP) instead of ARP.
* ARP is vulnerable to ARP Spoofing attacks.
