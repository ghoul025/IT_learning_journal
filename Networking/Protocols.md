# Networking Protocols

## Purpose

Networking protocols are standardized rules that allow devices to communicate.

Without protocols, devices would have no common method for:

- Identifying destinations
- Exchanging information
- Requesting services
- Resolving addresses
- Delivering data
- Reporting errors

Protocols ensure that systems from different vendors, operating systems, and environments can communicate consistently.

---

# Protocol Categories

Networking protocols generally perform one of the following functions:

- Address Resolution
- Network Configuration
- Data Delivery
- Name Resolution
- Service Access
- Diagnostics
- Remote Access
- Security
- Time Synchronization

Understanding a protocol's purpose is more important than memorizing technical details.

---

# Ports

A port identifies a specific service or application running on a device.

While an IP address identifies a host, a port identifies a process or service on that host.

Example:

```text
IP Address = Building Address

Port = Room Number
```

Ports allow multiple services to operate simultaneously on a single device.

Examples:

```text
Web Service
Email Service
File Service
Remote Access Service
```

Ports exist at the Transport Layer and are primarily associated with TCP and UDP communication.

---

# Common Ports

The following ports are commonly encountered during troubleshooting and system administration.

| Port | Protocol | Service | Purpose |
|--------|----------|----------|----------|
| 20/21 | TCP | FTP | File Transfer |
| 22 | TCP | SSH | Secure Remote Access |
| 23 | TCP | Telnet | Remote Access (Legacy) |
| 25 | TCP | SMTP | Email Sending |
| 53 | TCP/UDP | DNS | Name Resolution |
| 67/68 | UDP | DHCP | Automatic IP Configuration |
| 80 | TCP | HTTP | Web Traffic |
| 88 | TCP/UDP | Kerberos | Authentication |
| 110 | TCP | POP3 | Email Retrieval |
| 123 | UDP | NTP | Time Synchronization |
| 135 | TCP | RPC | Windows Remote Services |
| 137-139 | TCP/UDP | NetBIOS | Legacy Windows Networking |
| 143 | TCP | IMAP | Email Retrieval |
| 161/162 | UDP | SNMP | Monitoring and Management |
| 389 | TCP/UDP | LDAP | Directory Services |
| 443 | TCP | HTTPS | Secure Web Traffic |
| 445 | TCP | SMB | Windows File Sharing |
| 514 | UDP | Syslog | Log Collection |
| 636 | TCP | LDAPS | Secure Directory Services |
| 3389 | TCP | RDP | Windows Remote Desktop |

---

## Port Types

Ports are commonly divided into three ranges.

| Range | Category |
|---------|------------|
| 0-1023 | Well-Known Ports |
| 1024-49151 | Registered Ports |
| 49152-65535 | Dynamic / Ephemeral Ports |

Most services commonly encountered during administration and troubleshooting use well-known ports.

---

# TCP

Transmission Control Protocol (TCP) is a connection-oriented transport protocol.

Purpose:

```text
Reliable Delivery
```

Characteristics:

- Connection-oriented
- Acknowledges received data
- Detects missing data
- Maintains data order
- Retransmits lost data

Common use cases:

- Traditional Web Applications
- Email
- File Transfers
- Remote Administration

When reliability is more important than speed, TCP is typically used.

---

# UDP

User Datagram Protocol (UDP) is a connectionless transport protocol.

Purpose:

```text
Fast Delivery
```

Characteristics:

- Connectionless
- No delivery confirmation
- No retransmission
- Lower overhead
- Faster communication

Common use cases:

- DNS Queries
- Voice Communication
- Video Streaming
- Online Gaming
- Real-Time Services

When speed is more important than reliability, UDP is often used.

---

# TCP vs UDP

```text
TCP
=
Reliable
Ordered
Acknowledged
Higher Overhead

UDP
=
Fast
Lightweight
Unacknowledged
Lower Overhead
```

Both protocols serve different purposes and are selected based on application requirements.

---

# ARP

Address Resolution Protocol (ARP) resolves a logical address to a physical address on a local network.

Purpose:

```text
IP Address → MAC Address
```

Before a device can communicate with another device on the same network, it must determine the destination MAC address.

ARP performs this mapping automatically.

---

# DHCP

Dynamic Host Configuration Protocol (DHCP) automatically assigns network configuration information to devices.

Common information provided:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Servers

Purpose:

```text
Automatic Network Configuration
```

Without DHCP, devices would require manual configuration.

---

# DNS

Domain Name System (DNS) translates human-readable names into IP addresses.

Example:

```text
google.com
↓
142.250.x.x
```

Purpose:

```text
Name Resolution
```

Humans use names.

Networks use addresses.

DNS bridges the gap between the two.

---

# ICMP

Internet Control Message Protocol (ICMP) provides diagnostic and error-reporting functions.

Purpose:

```text
Network Diagnostics
```

Common uses:

- Ping
- Connectivity Testing
- Error Reporting
- Path Verification

ICMP helps administrators determine network reachability and identify communication issues.

---

# Default Gateway

A default gateway is the path a device uses to reach networks outside its local network.

Conceptually:

```text
Local Device
      ↓
Default Gateway
      ↓
Remote Network
```

Without a default gateway, communication is limited to the local network.

---

# Routing

Routing is the process of determining the path data should take between networks.

Purpose:

```text
Network-to-Network Communication
```

Routers examine addressing information and forward traffic toward its destination.

Routing allows communication beyond a single network segment.

---

# NAT

Network Address Translation (NAT) modifies addressing information as traffic passes through a network device.

Common purpose:

```text
Private Address
↓
Public Address
```

Benefits:

- Conserves public IP addresses
- Enables Internet access for private networks
- Adds basic address abstraction

NAT is commonly performed by routers, firewalls, and other gateway devices.

---

# VPN

A Virtual Private Network (VPN) creates a secure connection across another network.

Purpose:

```text
Secure Remote Communication
```

Common use cases:

- Remote Work
- Site-to-Site Connectivity
- Secure Administrative Access

Most VPN implementations use encryption to protect data while it travels across untrusted networks.

---

# Application Protocols

Application protocols provide services directly consumed by users and applications.

These protocols rely on lower-layer networking protocols to function.

---

## HTTP

Hypertext Transfer Protocol.

Purpose:

```text
Website Communication
```

HTTP is used to transfer web content between clients and web servers.

HTTP traffic is not encrypted.

---

## HTTPS

Hypertext Transfer Protocol Secure.

Purpose:

```text
Secure Website Communication
```

HTTPS provides encryption and identity verification for web traffic.

Most modern websites use HTTPS.

---

## SSH

Secure Shell.

Purpose:

```text
Secure Remote Administration
```

SSH allows administrators to remotely access and manage systems securely.

Common uses:

- Remote Terminal Access
- System Administration
- Secure File Transfers
- Automation Tasks

---

## FTP

File Transfer Protocol.

Purpose:

```text
File Transfers
```

FTP allows files to be transferred between systems.

Traditional FTP does not encrypt traffic.

---

## SFTP

SSH File Transfer Protocol.

Purpose:

```text
Secure File Transfers
```

SFTP provides encrypted file transfer capabilities using SSH.

---

# Supporting Services

The following services are commonly found in enterprise environments and support network operations.

---

## NTP

Network Time Protocol.

Purpose:

```text
Time Synchronization
```

Accurate time is important for:

- Logging
- Authentication
- Monitoring
- Troubleshooting

---

## SNMP

Simple Network Management Protocol.

Purpose:

```text
Monitoring and Management
```

SNMP is used to collect information from network devices and systems.

Common monitoring targets:

- Device Health
- Interface Status
- Resource Utilization
- Performance Metrics

---

# Communication Flow Example

A simplified web request:

```text
User enters website name
        ↓
DNS resolves name to IP address
        ↓
ARP resolves local MAC address
        ↓
Traffic is sent to the default gateway
        ↓
Routers forward traffic toward destination
        ↓
TCP establishes communication
        ↓
HTTPS transfers encrypted data
        ↓
Server responds
        ↓
TCP confirms delivery
```

Multiple protocols work together to complete a single network operation.

---

# Key Takeaways

The most important transport protocols are:

- TCP
- UDP

The most important infrastructure protocols are:

- ARP
- DHCP
- DNS
- ICMP

The most important networking concepts built on top of these are:

- Ports
- Default Gateway
- Routing
- NAT
- VPN

The most common application and operational protocols are:

- HTTP
- HTTPS
- SSH
- FTP
- SFTP
- NTP
- SNMP

Most real-world networking issues can be traced to one or more of these components.

Understanding how they interact provides the foundation for effective troubleshooting, system administration, and network operations.
