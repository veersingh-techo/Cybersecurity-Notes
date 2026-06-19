# Networking Notes

> Notes created while studying Cisco Networking Basics and later expanded with concepts from HTB Academy Introduction to Networking.

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
- hexadecimal
- 128-bit Address
- Larger Address Space
- Better Efficiency
- Improved Security

## Commands

### Windows

```cmd
ipconfig
```

### Linux

```bash
ip -6 addr
```

```bash
ping6 google.com
```
## IPv4 vs IPv6

| IPv4 | IPv6 |
|--------|--------|
| 32-bit | 128-bit |
| Example: 192.168.1.1 | Example: 2001:db8::1 |
| Uses NAT | Usually no NAT |
| Limited addresses | Huge address space |

---
# MAC Address
MAC address addresses the physical connection (network card, Bluetooth, or WLAN adapter) of a host. Each network card has its individual MAC address, which is configured once on the manufacturer's hardware side but can always be changed, at least temporarily.
48 bits aur 6 octet ka hota hai.
## Attacks
- Mac spoofing
- mac flooding
- mac add filtering.
---

# Address Resolution Protocol (ARP)

## Definition
ARP (Address Resolution Protocol) is used to find the MAC address associated with an IPv4 address on a local network.

## How ARP Works

1. Device sends an ARP Request (broadcast).
2. The target device receives the request.
3. The target sends an ARP Reply containing its MAC address.
4. Communication can now occur using MAC addresses.

## Types

- ARP Request
- ARP Reply

## Commands

arp -a

Displays the ARP cache table.

```bash
ip neigh
```

Shows ARP entries in Linux.

## Cybersecurity Relevance

- ARP Spoofing
- ARP Poisoning
- Man-in-the-Middle (MITM) Attacks
- Network Traffic Interception

## Common Tools

- Ettercap
- Bettercap
- Wireshark

## Key Takeaways

- ARP maps IP addresses to MAC addresses.
- Works only within a local network (LAN).
- Uses broadcast requests and unicast replies.
- Frequently abused in MITM attacks.
---

# CIDR

CIDR (Classless Inter-Domain Routing) specifies how many bits of an IP address are reserved for the network portion.
---

# Common Network Protocols

| Protocol | Port | Definition |
|----------|------|------------|
| SSH | 22 | Secure protocol used for remote login and command execution. |
| FTP | 21 | Protocol used to transfer files between systems. |
| SMTP | 25 | Protocol used to send emails between mail servers. |
| HTTP | 80 | Protocol used for transferring web pages and web content. |
| HTTPS | 443 | Secure version of HTTP that uses SSL/TLS encryption. |
| SMB | 445 | Protocol used for file and printer sharing in Windows networks. |
| DNS | 53 | Protocol that converts domain names into IP addresses. |
| DHCP | 67/68 | Protocol that automatically assigns IP addresses to devices. |
| SNMP | 161/162 | Protocol used to monitor and manage network devices. |
| NTP | 123 | Protocol used to synchronize time across network devices. |
| VPN | N/A | Technology used to create a secure encrypted connection over the Internet. |
| IPsec | N/A | Security protocol suite that encrypts and authenticates network traffic. |
| NAT | N/A | Technology that translates private IP addresses into public IP addresses. |

## Cybersecurity Relevance

### SSH (22)
- Secure remote administration
- Common brute-force target

### FTP (21)
- Credentials often sent in plaintext
- Frequently misconfigured

### SMTP (25)
- Email spoofing
- Phishing infrastructure

### HTTP (80)
- Web application attacks
- SQL Injection
- Cross-Site Scripting (XSS)

### HTTPS (443)
- SSL/TLS encryption
- Certificate validation

### SMB (445)
- Enumeration target
- Used in many Windows attacks

### DNS (53)
- DNS Enumeration
- DNS Spoofing
- DNS Tunneling

### DHCP (67/68)
- Rogue DHCP attacks
- Automatic IP assignment

### SNMP (161/162)
- Network device enumeration
- Information disclosure

### NTP (123)
- NTP amplification attacks
- Important for accurate security logs

### VPN
- Secure remote access
- Traffic encryption

### IPsec
- VPN security
- Secure site-to-site communication

### NAT
- Hides internal network structure
- Conserves public IP addresses
---
# Additional Important Protocols

## TCP

Connection-oriented protocol that provides reliable communication using a Three-Way Handshake.

### Key Points
- Reliable
- Ordered delivery
- Uses handshake

### Cybersecurity Relevance
- SYN Flood attacks
- Port scanning

---

## UDP

Connectionless protocol that prioritizes speed over reliability.

### Key Points
- Fast
- No handshake
- No retransmission

### Cybersecurity Relevance
- UDP Flood attacks

---

## ICMP

Used for network diagnostics and error reporting.

### Key Points
- Used by ping
- Used by traceroute
- Reports network errors

### Cybersecurity Relevance
- Host discovery
- Network reconnaissance

---

## RDP (3389)

Protocol for remote access to Windows systems.

### Cybersecurity Relevance
- Common brute-force target
- Frequently targeted by attackers

---

## LDAP (389)

Used to access and manage directory services such as Active Directory.

### Cybersecurity Relevance
- User enumeration
- Active Directory attacks

---

## Kerberos (88)

Authentication protocol used in Active Directory environments.

### Cybersecurity Relevance
- Kerberoasting attacks
- Domain authentication

---

## POP3 (110)

Downloads emails from a mail server to a device.

---

## IMAP (143)

Synchronizes emails across multiple devices.

---

## OSPF

Dynamic routing protocol used by routers to exchange routes.

---

## MySQL (3306)

Database service commonly found on web servers.

### Cybersecurity Relevance
- SQL Injection targets

## Quick Comparison: TCP vs UDP

| Feature | TCP | UDP |
|----------|----------|----------|
| Connection | Connection-Oriented | Connectionless |
| Reliability | Reliable | Less Reliable |
| Speed | Slower | Faster |
| Packet Ordering | Yes | No |
| Retransmission | Yes | No |
| Examples | HTTP, HTTPS, SSH | DNS, DHCP, NTP |
---
# Wireless Networks (WiFi)

WiFi is a wireless networking technology based on the IEEE 802.11 standard that allows devices to communicate without cables.

## Important Terms

### SSID
- Name of a WiFi network.
- Example: Home_WiFi

### Access Point (AP)
- Device that provides wireless connectivity.
- Usually a WiFi router.

## WiFi Security

### WEP
- Old WiFi security protocol.
- Uses RC4 encryption.
- Vulnerable to attacks.

### WPA2
- Uses AES encryption.
- Secure and widely used.

### WPA3
- Latest and most secure WiFi standard.
- Better protection against password attacks.

---

## Cybersecurity Relevance

- Weak WiFi passwords can be cracked.
- WEP is insecure and should be avoided.
- MAC addresses can be spoofed.
- Rogue Access Points can be used for attacks.

### Key Takeaway
Use WPA2 or WPA3. Avoid WEP.
---
# vpn
Internet Protocol Security (IPsec) is a network security protocol that provides encryption and authentication for internet communications
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