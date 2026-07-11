# 📡 Network Traffic Analysis using Wireshark

## 📌 Project Overview

This project demonstrates hands-on network traffic analysis using **Wireshark** in a virtual lab environment. Traffic was generated between Kali Linux, Windows 10, and external web servers, then captured and analyzed to understand how common network protocols operate.

The project focuses on identifying packet structures, protocol behavior, and communication patterns commonly encountered by SOC (Security Operations Center) analysts.

---

## 🎯 Objectives

- Capture live network traffic using Wireshark
- Analyze common networking protocols
- Understand packet flow and protocol behavior
- Learn TCP/IP communication
- Develop practical packet analysis skills
- Build a portfolio project for entry-level SOC Analyst roles

---

## 🛠️ Lab Environment

| Component | Details |
|-----------|---------|
| Hypervisor | VMware Workstation |
| Attacker/Analysis Machine | Kali Linux |
| Target Machine | Windows 10 |
| Packet Analyzer | Wireshark |
| Network Type | NAT Network |

---

# 🔧 Tools Used

- Wireshark
- Kali Linux
- Windows 10
- VMware Workstation
- Ping
- nslookup
- Firefox Browser

---

# 📂 Protocols Analyzed

## ✅ ICMP (Ping)

### Purpose
Verify connectivity between Kali Linux and Windows 10.

### Observation

- Successful Echo Request and Echo Reply
- No packet loss
- TTL = 128 (Windows)
- Low latency

**Wireshark Filter**

```text
icmp
```

---

## ✅ DNS

### Purpose

Resolve domain names into IP addresses.

### Observation

- Generated using:

```bash
nslookup google.com
```

- DNS queries sent to DNS server
- Multiple IPv4 and IPv6 addresses returned
- Communication over UDP Port 53

**Wireshark Filter**

```text
dns
```

---

## ✅ HTTP

### Purpose

Analyze unencrypted web traffic.

### Observation

- HTTP GET request captured
- HTTP/1.1 200 OK response received
- Request-response communication observed

**Wireshark Filter**

```text
http
```

---

## ✅ HTTPS / TLS

### Purpose

Analyze encrypted web communication.

### Observation

- TLS 1.2 and TLS 1.3 traffic captured
- TLS handshake observed
- Encrypted Application Data exchanged
- Communication with Google servers

**Wireshark Filter**

```text
tls
```

---

## ✅ TCP

### Purpose

Study reliable communication and connection establishment.

### Observation

Captured complete TCP Three-Way Handshake

```
SYN
↓

SYN-ACK
↓

ACK
```

Also observed

- HTTP communication
- Connection termination (FIN, ACK)

**Wireshark Filter**

```text
tcp
```

---

## ✅ UDP

### Purpose

Analyze connectionless communication.

### Observation

- DNS over UDP
- Source Port → Ephemeral Port
- Destination Port → 53
- mDNS traffic observed

**Wireshark Filter**

```text
udp
```

---

## ✅ ARP

### Purpose

Understand IP-to-MAC address resolution.

### Observation

Captured

- ARP Requests
- ARP Replies
- ARP Probes
- ARP Announcements

Example

```
Who has 192.168.32.2?

Tell 192.168.32.136
```

**Wireshark Filter**

```text
arp
```

---

# 📊 Key Findings

- Successfully captured live network traffic
- Verified communication between virtual machines
- Analyzed seven common networking protocols
- Observed TCP Three-Way Handshake
- Studied encrypted HTTPS communication
- Understood DNS query and response process
- Learned ARP-based MAC address resolution
- Practiced packet filtering and protocol analysis

---

# 📁 Project Structure

```
Network-Traffic-Analysis-Wireshark/
│
├── README.md
├── Report/
│   └── Network_Traffic_Analysis_Wireshark_Report.pdf
│
├── Captures/
│   ├── icmp_capture.pcapng
│   ├── dns_capture.pcapng
│   ├── http_capture.pcapng
│   ├── https_tls_capture.pcapng
│   ├── tcp_capture.pcapng
│   ├── udp_capture.pcapng
│   └── arp_capture.pcapng
│
├── Screenshots/
│   ├── icmp.png
│   ├── dns.png
│   ├── http.png
│   ├── tls.png
│   ├── tcp.png
│   ├── udp.png
│   └── arp.png
│
└── LICENSE
```

---

# 🎓 Skills Demonstrated

- Packet Capture
- Packet Inspection
- TCP/IP Networking
- DNS Analysis
- HTTP Analysis
- HTTPS/TLS Analysis
- TCP Three-Way Handshake
- UDP Analysis
- ARP Analysis
- Network Troubleshooting
- Wireshark Filtering
- Cybersecurity Fundamentals

---

# 💼 SOC Analyst Skills Gained

- Traffic Monitoring
- Packet Analysis
- Protocol Identification
- Network Troubleshooting
- Basic Threat Investigation
- Understanding Client-Server Communication
- Log Interpretation
- Network Visibility

---

# 🚀 Future Improvements

- Analyze FTP traffic
- Analyze SSH traffic
- Analyze DHCP traffic
- Detect ARP Spoofing attacks
- Investigate DNS Tunneling
- Perform Malware Traffic Analysis
- Export packet statistics and protocol hierarchy

---

# 📚 References

- Wireshark Documentation
- RFC 791 – Internet Protocol (IP)
- RFC 792 – ICMP
- RFC 793 – TCP
- RFC 768 – UDP
- RFC 1035 – DNS
- RFC 826 – ARP

---

## 👩‍💻 Author

**Ankita Saxena**

PG Diploma in Cybersecurity

Aspiring SOC Analyst | Network Security Enthusiast | Wireshark Learner

GitHub: https://github.com/SaXen0Shield0WebGuard

