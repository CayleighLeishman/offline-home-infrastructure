# CCNA Home Lab: My Digital Library Syllabus

*A roadmap of everything I learned about network architecture, security, and carrier bypass.*

---

## Table of Contents

<details>
<summary>Lab Topics</summary>

1. [Private vs. Public IP (NAT)](#private-vs-public-ip-nat)
2. [The TTL Cloaking Trick (Layer 3)](#the-ttl-cloaking-trick-layer-3)
3. [Alternative Connection Methods](#alternative-connection-methods)
4. [SSH Keys & Asymmetric Encryption](#ssh-keys--asymmetric-encryption)
5. [Media Streaming & Proxy Risks](#media-streaming--proxy-risks)
6. [Star Topology vs. Daisy Chaining](#star-topology-vs-daisy-chaining)
7. [Infrastructure vs. Peripherals](#infrastructure-vs-peripherals)
8. [Attenuation & Signal Physics](#attenuation--signal-physics)
9. [OS Personalities (Security Guards)](#os-personalities-security-guards)
10. [The OSI Model (The 7 Layers)](#the-osi-model-the-7-layers)
11. [Encapsulation (The Data Envelope)](#encapsulation-the-data-envelope)
12. [DHCP vs. Static IP Addressing](#dhcp-vs-static-ip-addressing)
13. [The Default Gateway (Exit Signs)](#the-default-gateway-exit-signs)
14. [Connectivity Testing (ICMP/Ping)](#connectivity-testing-icmpping)
15. [TCP vs. UDP (Transport Logistics)](#tcp-vs-udp-transport-logistics)
16. [Subnetting & Masks (Neighborhood Slicing)](#subnetting--masks-neighborhood-slicing)
17. [IPv6: The Infinite Address Space](#ipv6-the-infinite-address-space)
18. [Troubleshooting Flowchart](#troubleshooting-flowchart)
</details>

<details>
<summary>Glossary</summary>

- [A](#a)  
- [D](#d)  
- [E](#e)  
- [F](#f)  
- [H](#h)  
- [I](#i)  
- [M](#m)  
- [N](#n)  
- [S](#s)  
- [T](#t)  
- [U](#u)  
</details>

---

## Lab Sections

### Private vs. Public IP (NAT)
*Internal "Room Numbers" vs. External "Building Address."*

**Key Learnings:**  
- Private IPs (192.168.x.x) safe for diagrams  
- NAT (Network Address Translation) shares one public IP across devices  

**Commands:**  
```bash
ifconfig
ip addr show
````

---

### The TTL Cloaking Trick (Layer 3)

*Bypassing carrier hotspot detection by modifying packet headers.*

**Key Learnings:**

* TTL = "Time To Live" on packets
* Setting TTL to 65 makes it appear as 64 to the carrier

**Commands:**

```bash
sudo sysctl -w net.ipv4.ip_default_ttl=65
```

---

### Alternative Connection Methods

*Finding "Secret Roads" when Wi-Fi Hotspot is locked.*

* USB Tethering: bypasses blocks
* Bluetooth: low speed, high stealth
* NetShare (Android): WiFi-Direct proxy

---

### SSH Keys & Asymmetric Encryption

*"Magic Padlocks" instead of weak passwords.*

* Public Key = server padlock
* Private Key = master key on your device
* Brute-force protection + automation

**Commands:**

```bash
ssh-keygen -t ed25519
```

---

### Media Streaming & Proxy Risks

* Jellyfin: local Netflix-style server
* Proxy Risks: NetShare can see unencrypted traffic
* Offline Mode: stream without internet

---

### Star Topology vs. Daisy Chaining

* Central Hub: phone or switch in the middle of the star
* Ethernet: fast, stable, full-duplex
* Static IPs: manual addressing if no router

---

### Infrastructure vs. Peripherals

**Peripheral Connections:** USB, Lightning, Bluetooth – point-to-point, limited

**Network Infrastructure:** Ethernet, switches, access points – multipoint, fast, simple

---

### Attenuation & Signal Physics

* Loss of signal strength over distance
* USB/Lightning: fails after ~15ft
* Ethernet: reliable to 100m
* Wi-Fi: attenuates through walls & interference

---

### OS Personalities (Security Guards)

| OS            | Personality  | Behavior                            |
| ------------- | ------------ | ----------------------------------- |
| ChromeOS      | Scientist    | Developer Mode needed for TTL edits |
| Android       | Tinkerer     | Allows apps like NetShare           |
| iOS           | Guard        | Resets TTL, blocks toggles          |
| Windows/Linux | Professional | Full Ethernet & static IP control   |

---

### The OSI Model (The 7 Layers)

| Layer | Name        | Activity                             |
| ----- | ----------- | ------------------------------------ |
| 7     | Application | Jellyfin, SSH, Samba                 |
| 4     | Transport   | Port numbers (SSH 22, Jellyfin 8096) |
| 3     | Network     | TTL edits, IP assignments            |
| 2     | Data Link   | MAC addresses via switch             |
| 1     | Physical    | Compare Ethernet vs USB, attenuation |

---

### Encapsulation (The Data Envelope)

* Data → Segment → Packet → Frame
* TTL editing = writing on the envelope

---

### DHCP vs. Static IP Addressing

* DHCP = "Librarian" hands out addresses automatically
* Static IP = manually assign server addresses

---

### The Default Gateway (Exit Signs)

* IP of device leading to Internet
* Android phone = default gateway

---

### Connectivity Testing (ICMP/Ping)

* Protocol: ICMP
* Command:

```bash
ping <Target_IP_Address>
```

* Echo reply confirms Layer 3 connectivity

---

### TCP vs. UDP (Transport Logistics)

* TCP = Certified mail (reliable)
* UDP = Standard post (fast, lossy)

---

### Subnetting & Masks (Neighborhood Slicing)

* Subnet mask = network vs host
* /24 notation = first 3 chunks = network

---

### IPv6: The Infinite Address Space

* From 4B (IPv4) → 340 undecillion (IPv6)
* Link-local: fe80::
* No NAT needed

**Command:**

```bash
ip -6 addr
```

---

### Troubleshooting Flowchart

1. Physical → cable & hotspot
2. Data Link → MAC visibility
3. Network → IP + ping gateway
4. Application → Jellyfin running

---

## Glossary
<summary>Glossary</summary>

- [A](#a)  
- [D](#d)  
- [E](#e)  
- [F](#f)  
- [H](#h)  
- [I](#i)  
- [M](#m)  
- [N](#n)  
- [S](#s)  
- [T](#t)  
- [U](#u)  
</details>

### A

* **Access Point (AP):** creates a WLAN
* **Attenuation:** signal weakening over distance

### D

* **Default Gateway:** exit sign for network
* **Degree:** How Many Edges Connect to a Vertex
* **DHCP:** automatically assigns IPs
* **Dual Stack:** IPv4 + IPv6 simultaneously

### E
* **Edges:** a line (or road) that connects two vertices.
* **Encapsulation:** wrapping data for transmission
* **Ethernet:** wired Cat6 network

### F

* **Full-Duplex:** send & receive at same time

### H

* **Half-Duplex:** only one device at a time
* **Hexadecimal:** 0–9 & A–F, IPv6

### I

* **ICMP:** protocol behind ping
* **IPv6:** infinite address space

### M

* **MAC Address:** permanent device ID

### N

* **NAT:** hides private IPs behind one public IP

### S

* **SLAAC:** auto IPv6 assignment
* **Socket:** IP + port
* **Subnet Mask:** network vs host

### T

* **TCP:** reliable delivery with handshake
* **TTL:** prevents packet loops

### U

* **UDP:** fast, unreliable delivery

### V
*  **vertices:** More than one Vertex.
*  **Vertex:** single point (or node) in a network or graph where connections (edges) meet. 

