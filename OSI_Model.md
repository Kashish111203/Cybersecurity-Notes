# OSI Model Notes

**Date:** 03-06-2026

## What is OSI Model?

OSI (Open Systems Interconnection) Model is a conceptual framework used to understand communication between computer systems over a network. It was developed by ISO(International Standards organisation) in 1984.

---

# 7 Layers of OSI Model

## 7. Application Layer

* Provides services directly to users
* Examples: HTTP, FTP, SMTP
* Used by networking apps like browsers, outlook, skype etc.

## 6. Presentation Layer

* Performs Translation, Compression, Encryption
* For Encryption uses SSL

## 5. Session Layer

* Creates, manages and terminates sessions
* It also keeps track of the files being downloaded

## 4. Transport Layer

* Performs Error control, Flow control, Segmentation
* Provides two types of services: Connection oriented and connectionless services
* Responsible for reliable communication
* Protocols: TCP, UDP
* Basic data unit: Segments

## 3. Network Layer

* Handles routing and IP addressing/ Logical addressing
* Device: Router
* Basic data unit: IP Packets

## 2. Data Link Layer

* It performs access control
* Handles MAC addressing/Physical addressing and error detection
* Device: SwitchBasic data unit: Frame

## 1. Physical Layer

* Converts raw bits into signals
* Transfers signals through cables or wireless
* Devices: Hub, cables

---

# Important Points

* Sending: Layer 7 → Layer 1
* Receiving: Layer 1 → Layer 7
* Every layer performs a specific function

