# Networking Fundamentals

## Purpose

Networking exists to allow devices to communicate and exchange data.

Everything in networking, from browsing websites to cloud computing, is built upon the ability of devices to send, receive, and understand data.

At its core, networking answers four questions:

1. Who is communicating?
2. Where is the data going?
3. How does the data get there?
4. How do both sides understand each other?

---

# Core Components

## Host

A host is any device connected to a network.

Examples:

- Desktop Computer
- Laptop
- Smartphone
- Printer
- Server

A host can send, receive, or both send and receive data.

---

## Client

A client is a host that requests services or resources.

Example:

```text
Laptop requests a webpage.
```

The laptop is the client.

---

## Server

A server is a host that provides services or resources.

Example:

```text
Web Server provides a webpage.
```

The server responds to client requests.

---

## Network Devices

Network devices help move data between hosts.

Common examples:

- Switch
- Router
- Access Point
- Firewall

Their purpose is to ensure data reaches its destination.

---

# Addressing

For communication to occur, every device must have an identity.

Networking uses two primary addresses.

---

## IP Address

An IP address is a logical address assigned to a device.

Example:

```text
192.168.1.10
```

Purpose:

```text
Identifies where a device exists on a network.
```

An IP address can change.

---

## MAC Address

A MAC address is a physical hardware address assigned to a network interface.

Example:

```text
00:1A:2B:3C:4D:5E
```

Purpose:

```text
Identifies a specific network interface.
```

A MAC address is typically permanent.

---

## IP vs MAC

```text
IP Address
=
Logical Address
=
Used between networks

MAC Address
=
Physical Address
=
Used within local networks
```

Both are required for network communication.

---

# Types of Networks

## LAN

Local Area Network.

A network covering a small area.

Examples:

- Home Network
- Office Network
- Computer Lab

---

## WAN

Wide Area Network.

A network that connects multiple LANs.

Example:

```text
The Internet
```

---

## WLAN

Wireless Local Area Network.

A LAN that uses wireless communication.

Example:

```text
Wi-Fi
```

---

# Data Communication

Networking is the movement of data between devices.

The basic communication process is:

```text
Sender
↓
Data Transmission
↓
Receiver
```

Every network communication follows this same principle regardless of size.

---

# Data Encapsulation

When data travels across a network, it is divided into smaller units and wrapped with information that helps delivery.

Conceptually:

```text
Application Data
↓
Transport Information
↓
Network Information
↓
Frame Information
↓
Transmission
```

Each layer adds information required for successful communication.

This process is known as encapsulation.

---

# OSI Model

The OSI Model is a conceptual framework used to understand network communication.

```text
7 - Application
6 - Presentation
5 - Session
4 - Transport
3 - Network
2 - Data Link
1 - Physical
```

Purpose:

```text
Standardize how networking functions are understood.
```

The OSI Model is primarily used for learning and troubleshooting.

---

## Layer 1 – Physical

Responsible for transmitting raw signals.

Examples:

- Ethernet Cables
- Fiber Cables
- Wireless Signals
- Network Ports

Question:

```text
Can signals physically travel?
```

---

## Layer 2 – Data Link

Responsible for communication within the local network.

Uses:

```text
MAC Addresses
```

Question:

```text
Can devices communicate locally?
```

---

## Layer 3 – Network

Responsible for moving data between networks.

Uses:

```text
IP Addresses
```

Question:

```text
Can data reach another network?
```

---

## Layer 4 – Transport

Responsible for end-to-end communication.

Focus:

```text
Reliability
Flow Control
Segmentation
```

Question:

```text
Can data be delivered correctly?
```

---

## Layer 5 – Session

Responsible for establishing and maintaining communication sessions.

Question:

```text
Can the communication remain active?
```

---

## Layer 6 – Presentation

Responsible for preparing data in a format both sides understand.

Focus:

```text
Formatting
Encoding
Encryption
Compression
```

Question:

```text
Can both devices interpret the data?
```

---

## Layer 7 – Application

Responsible for providing network services to applications and users.

Question:

```text
Can the application communicate?
```

---

# TCP/IP Model

The TCP/IP Model is the practical networking model used today.

```text
Application
Transport
Internet
Network Access
```

OSI Mapping:

```text
OSI                     TCP/IP

Application
Presentation
Session               → Application

Transport             → Transport

Network               → Internet

Data Link
Physical              → Network Access
```

Understanding the TCP/IP Model explains how modern networks and the Internet operate.

---

# Fundamental Truths of Networking

These concepts never change regardless of technology:

1. Devices must be identifiable.
2. Devices must have a way to communicate.
3. Data must have a source and destination.
4. Data must travel through a transmission medium.
5. Data must follow agreed-upon rules.
6. Data often passes through multiple devices before reaching its destination.
7. Network communication can be analyzed in layers.
8. Every networking technology builds upon these principles.

---

# Key Takeaways

Networking is the science of moving data between devices.

The most important concepts to remember are:

- Hosts
- Clients and Servers
- Network Devices
- IP Addresses
- MAC Addresses
- LAN, WAN, and WLAN
- Data Communication
- Encapsulation
- OSI Model
- TCP/IP Model

Everything else in networking, including DNS, DHCP, Routing, Switching, VLANs, VPNs, Firewalls, Cloud Networking, and Network Security, is built on these foundations.
``
