# 💻 Commands Used in the Project

This document contains the commands used to generate network traffic for analysis using Wireshark.

---

# 🖥️ Lab Environment

| Component | Description |
|-----------|-------------|
| Hypervisor | VMware Workstation |
| Attacker/Analysis Machine | Kali Linux |
| Target Machine | Windows 10 |
| Packet Analyzer | Wireshark |

---

# 1️⃣ Check Network Configuration

## Kali Linux

```bash
ip addr
```

Displays the IP address and network interfaces.

---

## Windows

```cmd
ipconfig
```

Displays the Windows IP configuration.

---

# 2️⃣ Verify Network Connectivity (ICMP)

## Kali Linux

```bash
ping <Windows_IP_Address>
```

Example

```bash
ping 192.168.32.136
```

### Purpose

- Generates ICMP Echo Requests
- Verifies connectivity
- Captured using Wireshark

### Wireshark Filter

```text
icmp
```

---

# 3️⃣ DNS Traffic Generation

## Kali Linux

```bash
nslookup google.com
```

### Purpose

Generates DNS query and response packets.

### Wireshark Filter

```text
dns
```

---

# 4️⃣ HTTP Traffic Generation

Open Firefox and browse to

```text
http://example.com
```

### Purpose

Generates HTTP GET and HTTP Response packets.

### Wireshark Filter

```text
http
```

---

# 5️⃣ HTTPS / TLS Traffic Generation

Open Firefox and browse to

```text
https://www.google.com
```

### Purpose

Generates encrypted HTTPS traffic.

### Wireshark Filter

```text
tls
```

or

```text
ssl
```

---

# 6️⃣ TCP Traffic

TCP packets are automatically generated during:

- HTTP browsing
- HTTPS browsing
- DNS fallback (when required)

### Wireshark Filter

```text
tcp
```

Observed

- SYN
- SYN-ACK
- ACK
- FIN
- ACK

---

# 7️⃣ UDP Traffic

UDP packets were generated while performing DNS lookups.

Example

```bash
nslookup google.com
```

### Wireshark Filter

```text
udp
```

Observed

- UDP Source Port (Ephemeral)
- UDP Destination Port 53
- DNS Query
- DNS Response

---

# 8️⃣ ARP Traffic

ARP packets are automatically generated whenever a device needs to discover the MAC address associated with an IP address.

To trigger additional ARP traffic:

### Linux

```bash
ping 192.168.32.136
```

or clear the ARP cache:

```bash
sudo ip neigh flush all
```

### Windows

```cmd
arp -d *
```

Then

```cmd
ping <Linux_IP_Address>
```

### Wireshark Filter

```text
arp
```

Observed

- ARP Request
- ARP Reply
- ARP Probe
- ARP Announcement

---

# 9️⃣ Useful Wireshark Display Filters

| Protocol | Filter |
|----------|--------|
| ICMP | `icmp` |
| DNS | `dns` |
| HTTP | `http` |
| HTTPS / TLS | `tls` |
| TCP | `tcp` |
| UDP | `udp` |
| ARP | `arp` |

---

# 🔟 Capture Workflow

1. Start Wireshark.
2. Select the active network interface (`eth0` in the virtual machine).
3. Click **Start Capture**.
4. Generate traffic using the commands listed above.
5. Stop the capture.
6. Apply display filters to inspect specific protocols.
7. Analyze packet details and record observations.
8. Save the capture as a `.pcapng` file.

---

**Author:** Ankita Saxena  
**Project:** Network Traffic Analysis using Wireshark
