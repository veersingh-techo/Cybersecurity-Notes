# Networking Notes

> Notes created while studying Networking Fundamentals and Cisco Networking Basics.

## Table of Contents

1. Network Basics
2. OSI Model
3. TCP/IP Model
4. IPv4 Addressing
5. IPv6 Basics
6. DNS
7. DHCP
8. Routing
9. Switching
10. Common Protocols and Ports
11. Network Troubleshooting
12. Cybersecurity Relevance

---

# Network Basics

## What is a Network?

A network is a group of devices connected together to share data and resources.

Examples:
- Internet
- Home Wi-Fi
- Office Network

### Benefits

- File Sharing
- Resource Sharing
- Communication
- Centralized Management

---

# OSI Model

The OSI Model consists of 7 layers.

| Layer | Name |
|---------|---------|
| 7 | Application |
| 6 | Presentation |
| 5 | Session |
| 4 | Transport |
| 3 | Network |
| 2 | Data Link |
| 1 | Physical |

## Layer Functions

### Application Layer
Provides services to users and applications.

Examples:
- HTTP
- HTTPS
- FTP
- DNS

### Presentation Layer

Responsible for:
- Encryption
- Compression
- Data Translation

### Session Layer

Responsible for:
- Establishing Sessions
- Maintaining Sessions
- Terminating Sessions

### Transport Layer

Responsible for:
- End-to-End Communication
- Segmentation
- Reliability

Protocols:
- TCP
- UDP

### Network Layer

Responsible for:
- Logical Addressing
- Routing

Protocol:
- IP

### Data Link Layer

Responsible for:
- MAC Addressing
- Error Detection

### Physical Layer

Responsible for:
- Transmission of Bits
- Cables and Connectors

---

# TCP/IP Model

| Layer | Protocol Examples |
|---------|---------|
| Application | HTTP, DNS, FTP |
| Transport | TCP, UDP |
| Internet | IP, ICMP |
| Network Access | Ethernet |

---

# IPv4 Addressing

IPv4 Address:
```
192.168.1.10
```

IPv4 consists of:

- 32 Bits
- 4 Octets

Example:

```
192.168.1.1
```

---

## Private IPv4 Ranges

| Range |
|---------|
| 10.0.0.0 – 10.255.255.255 |
| 172.16.0.0 – 172.31.255.255 |
| 192.168.0.0 – 192.168.255.255 |

Private IPs are not routable on the internet.

---

## Public IP Address

A public IP is globally unique and accessible over the internet.

Assigned by:
- ISP

---

# IPv6 Basics

IPv6 Address Example:

```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

Features:

- 128-bit Address
- Larger Address Space
- Better Efficiency
- Improved Security

---

# DNS

DNS = Domain Name System

Purpose:

Converts:

```
google.com
```

into:

```
142.250.x.x
```

Without DNS, users would need to remember IP addresses.

---

# DHCP

DHCP = Dynamic Host Configuration Protocol

Purpose:

Automatically assigns:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

Benefits:

- Automation
- Reduced Errors
- Easy Management

---

# Routing

Routing is the process of forwarding packets between networks.

Device Used:

- Router

Functions:

- Path Selection
- Packet Forwarding
- Inter-network Communication

---

# Switching

Switches operate primarily at Layer 2.

Functions:

- Forward Frames
- Learn MAC Addresses
- Reduce Network Traffic

Advantages:

- Faster Communication
- Better Network Performance

---

# Common Protocols and Ports

| Protocol | Port |
|---------|---------|
| FTP | 20/21 |
| SSH | 22 |
| Telnet | 23 |
| SMTP | 25 |
| DNS | 53 |
| DHCP | 67/68 |
| HTTP | 80 |
| POP3 | 110 |
| IMAP | 143 |
| HTTPS | 443 |

---

# TCP vs UDP

## TCP

Features:

- Reliable
- Connection-Oriented
- Error Checking
- Ordered Delivery

Examples:

- HTTPS
- FTP
- SSH

---

## UDP

Features:

- Fast
- Connectionless
- No Delivery Guarantee

Examples:

- DNS
- VoIP
- Online Gaming

---

# Network Troubleshooting

## ping

Tests connectivity.

Example:

```bash
ping google.com
```

---

## ipconfig

Displays IP configuration.

Example:

```cmd
ipconfig
```

---

## tracert

Shows packet path.

Example:

```cmd
tracert google.com
```

---

## nslookup

Queries DNS records.

Example:

```cmd
nslookup google.com
```

---

## netstat

Displays active connections.

Example:

```cmd
netstat -an
```

---

# Cybersecurity Relevance

Networking is the foundation of cybersecurity.

Important Concepts:

- IP Addressing
- DNS
- TCP/IP
- Routing
- Switching
- Ports and Protocols

Cybersecurity Tools Using Networking Knowledge:

- Nmap
- Wireshark
- Burp Suite
- Metasploit
- Nessus

---

# Key Takeaways

- Understand the OSI Model.
- Learn TCP/IP thoroughly.
- Know common ports and protocols.
- Practice troubleshooting commands.
- Build strong networking fundamentals before penetration testing.

---

## Author

Veer Singh

BTech CSE | Cybersecurity Learner

Current Learning:
- Linux
- Networking
- Cybersecurity Fundamentals
- Python
