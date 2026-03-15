# CCNA Home Lab: My Digital Library Syllabus

*A roadmap of everything I learned regarding network architecture, security, and carrier bypass.*

---

## Table of Contents

1. [Private vs. Public IP (NAT)](https://www.google.com/search?q=%231-private-vs-public-ip-addresses)
2. [The TTL Cloaking Trick (Layer 3)](https://www.google.com/search?q=%232-the-ttl-cloaking-trick)
3. [Alternative Connection Methods](https://www.google.com/search?q=%233-alternative-connection-methods)
4. [SSH Keys & Asymmetric Encryption](https://www.google.com/search?q=%234-ssh-keys--security)
5. [Media Streaming & Proxy Risks](https://www.google.com/search?q=%235-media-streaming--proxies)
6. [Star Topology vs. Daisy Chaining](https://www.google.com/search?q=%236-star-topology--ethernet)
7. [Infrastructure vs. Peripherals](https://www.google.com/search?q=%237-infrastructure-vs-peripherals)
8. [Attenuation & Signal Physics](https://www.google.com/search?q=%238-attenuation-the-fading-whisper)
9. [OS Personalities (Security Guards)](https://www.google.com/search?q=%239-operating-systems-the-personalities)
10. [The OSI Model (The 7 Layers)](https://www.google.com/search?q=%2310-the-osi-model-context-theory)
11. [Encapsulation (The Data Envelope)](https://www.google.com/search?q=%2311-encapsulation-the-envelope-concept)
12. [DHCP vs. Static IP Addressing](https://www.google.com/search?q=%2312-dhcp-vs-static-ip)
13. [The Default Gateway (Exit Signs)](https://www.google.com/search?q=%2313-the-default-gateway-the-exit-sign)
14. [Connectivity Testing (ICMP/Ping)](https://www.google.com/search?q=%2314-connectivity-testing-icmp)
15. [TCP vs. UDP (Transport Logistics)](https://www.google.com/search?q=%2315-tcp-vs-udp-transport-logistics)
16. [Subnetting & Masks (Neighborhood Slicing)](https://www.google.com/search?q=%2316-subnetting--masks)
17. [IPv6: The Infinite Address Space](https://www.google.com/search?q=%2317-ipv6-the-infinite-address-space)
18. [Troubleshooting Flowchart](https://www.google.com/search?q=%2318-troubleshooting-flowchart)

---

## 1. Private vs. Public IP Addresses

* **Concept:** Internal "Room Numbers" vs. External "Building Address."
* **Key Learnings:** * Private IPs (192.168.x.x) are safe to share in diagrams.
* **NAT (Network Address Translation)** allows many devices to share one Public IP.


* **Commands:** `ifconfig` or `ip addr show`.

---

## 2. The TTL Cloaking Trick

* **Concept:** Bypassing carrier hotspot detection by modifying packet headers.
* **Key Learnings:**
* **TTL (Time To Live):** A "timer" on data packets.
* **The Hack:** Setting TTL to 65 so it arrives at the carrier as 64 (standard).


* **Commands:** `sudo sysctl -w net.ipv4.ip_default_ttl=65`.

---

## 3. Alternative Connection Methods

* **Concept:** Finding "Secret Roads" when the Wi-Fi Hotspot is locked.
* **Key Learnings:**
* **USB Tethering:** Often bypasses "Call Customer Service" blocks.
* **Bluetooth:** Low speed (Bicycle path) but high stealth.
* **NetShare (Android):** Uses WiFi-Direct to create a proxy-based link.



---

## 4. SSH Keys & Security

* **Concept:** Replacing weak passwords with "Magic Padlocks."
* **Key Learnings:**
* **Public Key:** The "Padlock" you put on the server.
* **Private Key:** The "Master Key" you keep on your ThinkPad.


* **Why?** Brute-force protection and automation.
* **Commands:** `ssh-keygen -t ed25519`.

---

## 5. Media Streaming & Proxies

* **Concept:** Hosting services on the local "Intranet."
* **Key Learnings:**
* **Jellyfin:** A local Netflix-style server.
* **Proxy Risks:** Proxies (like NetShare) can see your unencrypted traffic.
* **Offline Mode:** I don't need internet to stream from Chromebook to iPad.

---

## 6. Star Topology & Ethernet

* **Concept:** Building a professional "Star" network instead of a "Chain."
* **Key Learnings:**
* **Central Hub:** The phone or a switch acts as the middle of the star.
* **Ethernet:** The fastest, most stable "cord" that speaks **Full-Duplex**.
* **Static IPs:** Manual addressing when there is no "Router" to do it for me.

---

## 7. Infrastructure vs. Peripherals

* **Concept:** Moving from "plugging in a toy" to "building a network."

### Peripheral Connections (The "Cords")

* **Definition:** USB, Lightning, and Bluetooth.
* **Purpose:** Designed for **Point-to-Point** data (one device to one computer) and charging.
* **Limitations:** They lack "Routing Intelligence" and are easily blocked by OS-level restrictions.

### Network Infrastructure (The "Roads")

* **Definition:** Ethernet (Cat6), Switches, and Access Points.
* **Purpose:** Designed for **Multipoint-to-Multipoint** communication.
* **Benefit:** Infrastructure is "dumb" in the best way—it just moves data as fast as possible without asking the Carrier for permission.

---

## 8. Attenuation (The "Fading Whisper")

* **Definition:** The loss of signal strength as it travels through a medium (wire or air).
* **CCNA Fact:**
* **USB/Lightning:** High attenuation. Signals fail after ~15 feet.
* **Ethernet:** Low attenuation. Reliable up to **100 meters (328 feet)**.
* **Wi-Fi:** High attenuation through walls and interference from microwaves.

---

## 9. Operating Systems: The "Personalities"

Different OSs act as the "Security Guards" for your hardware.

| OS | Personality | Networking Behavior |
| --- | --- | --- |
| **ChromeOS (Linux)** | The Scientist | Allows deep command-line control (TTL edits) but hides them behind "Developer Mode." |
| **Android** | The Tinkerer | Open enough to allow apps like NetShare to create "Side Roads" (Proxies). |
| **iOS (iPhone)** | The Guard | Very strict. It resets TTL headers and blocks hotspot toggles if the SIM plan is missing. |
| **Windows/Linux** | The Professional | Provides full control over Ethernet and Static IPs without "permission" from a carrier. |

---

## 10. The OSI Model Context (Theory)

When troubleshooting my "Digital Library," I'm moving through the **OSI (Open Systems Interconnect) Model**.

| Layer | Name | Your Lab Activity |
| --- | --- | --- |
| **Layer 7** | Application | Running **Jellyfin**, **SSH**, or **Samba**. |
| **Layer 4** | Transport | Managing **Port Numbers** (e.g., SSH on Port 22, Jellyfin on 8096). |
| **Layer 3** | Network | Editing **TTL** values and assigning **IP Addresses**. |
| **Layer 2** | Data Link | Identifying devices by **MAC Address** via a Switch. |
| **Layer 1** | Physical | Comparing **Ethernet** vs. **USB** and managing **Attenuation**. |

---

## 11. Encapsulation: The "Envelope" Concept

Think of the data movement as a postal service. Each layer adds a new "wrapper" around the data.

1. **The Data:** My movie file (Jellyfin).
2. **The Segment (L4):** Chopping the movie into small pieces.
3. **The Packet (L3):** Putting the piece in an envelope with an **IP Address** and a **TTL** number.
* *Lab Note:* Changing the TTL to 65 is like "writing on the envelope" before the carrier sees it.


4. **The Frame (L2):** Putting that envelope in a delivery truck with a **MAC Address**.

---

## 12. DHCP vs. Static IP

In a network, devices need a way to get their "Name Tags" (IPs).

* **DHCP (Dynamic Host Configuration Protocol):** The "Librarian" (Router/Phone) automatically hands out addresses.
* **Static IP:** I manually assign a permanent address.
* **CCNA Best Practice:** Servers (Chromebook Library) should always use **Static IPs** so clients (iPad/iPhone) always know where to find them.



---

## 13. The Default Gateway (The "Exit Sign")

* **Definition:** The IP address of the device that leads to the "Outside World" (Internet).
* **In My Lab:**
* My **Android Phone** acts as the Default Gateway.
* If the Chromebook talks to the ThinkPad, it stays inside.
* If the Chromebook talks to Google.com, it heads for the **Default Gateway**.

---

## 14. Connectivity Testing (ICMP)

* **Protocol:** **ICMP** (Internet Control Message Protocol).
* **The Tool:** `ping`.
* **The Goal:** Sending an "echo request" to see if a device is alive.
* **Command:** `ping <Target_IP_Address>`
* **Result:** If I see "64 bytes from...", Layer 3 connectivity is confirmed.

---

## 15. TCP vs. UDP (Transport Logistics)

* **Concept:** "Certified Mail" vs. "Standard Post."
* **Key Learnings:**
* **TCP (Transmission Control Protocol):** Uses a **Three-Way Handshake** (SYN, SYN-ACK, ACK) to ensure every bit of the movie arrives.
* **UDP (User Datagram Protocol):** Sends data without checking. Faster, but "lossy"—great for live streams where speed beats perfection.

---

## 16. Subnetting & Masks

* **Concept:** Defining the boundaries of the "Neighborhood."
* **Key Learnings:**
* **Subnet Mask:** A filter that tells the computer which part of the IP is the **Network** (Neighborhood) and which is the **Host** (House Number).
* **The /24 notation:** A common shortcut meaning the first three chunks (192.168.1) are the Network name.

---

## 17. IPv6: The Infinite Address Space

* **Concept:** Moving from 4 billion addresses (IPv4) to 340 undecillion (IPv6).
* **Key Learnings:**
* **Link-Local:** Every device gives itself an address starting with **`fe80::`**.
* **Hexadecimal:** Uses 0-9 and A-F to represent 128-bit addresses.
* **No More NAT:** Every grain of sand can have its own public address.


* **Command:** `ip -6 addr`.

---

## 18. 🛠️ Troubleshooting Flowchart

Use this logic when the "Library" is down:

1. **Physical:** Is the cable plugged in? Is the Hotspot toggle on?
2. **Data Link:** Do I see a MAC address? Can I see the device in Bluetooth settings?
3. **Network:** Do I have an IP address? Can I **Ping** the gateway?
4. **Application:** Is the Jellyfin service actually running on the Chromebook?

---

# Glossary of CCNA Terms

**Jump to:** [A](#A) | [D](#D) | [E](#E) | [F](#F) | [G](#G) | [H](#H) | [I](#I) | [L](#L) | [M](#M) | [N](#N) | [P](#P) | [R](#R) | [S](#S) | [T](#T) | [W](#W)

---

## A

**Access Point (AP)** A device that creates a wireless local area network (WLAN).

**Attenuation** The natural weakening of a signal as it travels over a distance.

---

## D

**Default Gateway** The "Exit Sign" for my network; the IP of the router leading out.

**DHCP** The "Librarian" that automatically assigns IP addresses.

**Dual Stack** Running both IPv4 and IPv6 at the same time on one device.

---

## E

**Encapsulation** Wrapping data in headers (the envelope) as it moves down the OSI layers.

**Ethernet** Standard wired technology using Cat6 cables for stable communication.

---

## F

**Full-Duplex** Sending and receiving data at the exact same time.

---

## H

**Half-Duplex** Only one device can transmit at a time (like a walkie-talkie).

**Hexadecimal** Base-16 numbering (0-9, A-F) used to shorten IPv6 addresses.

---

## I

**ICMP** The engine behind `ping`; used for testing and error reporting.

**IPv6** The 128-bit replacement for IPv4, allowing for infinite addresses.

---

## M

**MAC Address** The permanent "Social Security Number" burned into a network card.

---

## N

**NAT** Hiding many private IPs behind one public IP address.

---

## S

**SLAAC** A feature where a device gives itself an IPv6 address without a DHCP server.

**Socket** An IP Address plus a Port Number (e.g., `192.168.1.5:8096`).

**Subnet Mask** A number that divides an IP address into Network and Host sections.

---

## T

**TCP** The "Reliable" delivery service that uses a three-way handshake.

**TTL (Time To Live)** A value in the IP header that prevents packets from looping forever.

---

## U

**UDP** The "Fast" delivery service that doesn't check for errors.

---

**Now that the formatting is cleaner, would you like me to add a section for "Common Ports" (like 22 for SSH and 80 for HTTP) into the Glossary?**
