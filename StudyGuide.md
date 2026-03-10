# CCNA Home Lab: My Digital Library Syllabus
*A roadmap of everything I learned regarding network architecture, security, and carrier bypass.*

---

## Table of Contents (Click to Jump)
1. [ Private vs. Public IP (NAT)](#section-1)
2. [ The TTL Cloaking Trick (Layer 3)](#section-2)
3. [ Alternative Connection Methods](#section-3)
4. [ SSH Keys & Asymmetric Encryption](#section-4)
5. [ Media Streaming & Proxy Risks](#section-5)
6. [Star Topology vs. Daisy Chaining](#section-6)
7. [Infrastructure vs. Peripherals](#section-7)
8. [Attenuation & Signal Physics](#section-8)
9. [OS Personalities (Security Guards)](#section-9)
10. [The OSI Model (The 7 Layers)](#section-10)
11. [Encapsulation (The Data Envelope)](#section-11)
12. [DHCP vs. Static IP Addressing](#section-12)
13. [The Default Gateway (Exit Signs)](#section-13)
14. [Connectivity Testing (ICMP/Ping)](#section-14)
15. [Troubleshooting Flowchart](#section-15)

[Glossary](#glossary)

---

<a name="section-1"></a>
## 1. Private vs. Public IP Addresses
* **Concept:** Internal "Room Numbers" vs. External "Building Address."
* **Key Learnings:** * Private IPs (192.168.x.x) are safe to share in diagrams.
    * **NAT (Network Address Translation)** allows many devices to share one Public IP.
* **Commands:** `ifconfig` or `ip addr show`.
---

<a name="section-2"></a>
## 2. The TTL Cloaking Trick
* **Concept:** Bypassing carrier hotspot detection by modifying packet headers.
* **Key Learnings:**
    * **TTL (Time To Live):** A "timer" on data packets.
    * **The Hack:** Setting TTL to 65 so it arrives at the carrier as 64 (standard).
* **Commands:** `sudo sysctl -w net.ipv4.ip_default_ttl=65`.

---

<a name="section-3"></a>
## 3. Alternative Connection Methods
* **Concept:** Finding "Secret Roads" when the Wi-Fi Hotspot is locked.
* **Key Learnings:**
    * **USB Tethering:** Often bypasses "Call Customer Service" blocks.
    * **Bluetooth:** Low speed (Bicycle path) but high stealth.
    * **NetShare (Android):** Uses WiFi-Direct to create a proxy-based link.

---

<a name="section-4"></a>
## 4. SSH Keys & Security
* **Concept:** Replacing weak passwords with "Magic Padlocks."
* **Key Learnings:**
    * **Public Key:** The "Padlock" you put on the server.
    * **Private Key:** The "Master Key" you keep on your ThinkPad.
    * **Why?** Brute-force protection and automation.
* **Commands:** `ssh-keygen -t ed25519`.

---

<a name="section-5"></a>
## 5. Media Streaming & Proxies
* **Concept:** Hosting services on the local "Intranet."
* **Key Learnings:**
    * **Jellyfin:** A local Netflix-style server.
    * **Proxy Risks:** Proxies (like NetShare) can see your unencrypted traffic.
    * **Offline Mode:** I don't need internet to stream from Chromebook to iPad.

---

<a name="section-6"></a>
## 6. Star Topology & Ethernet
* **Concept:** Building a professional "Star" network instead of a "Chain."
* **Key Learnings:**
    * **Central Hub:** The phone or a switch acts as the middle of the star.
    * **Ethernet:** The fastest, most stable "cord" that speaks **Full-Duplex**.
    * **Static IPs:** Manual addressing when there is no "Router" to do it for me.
---

<a name="section-7"></a>
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

<a name="section-8"></a>
## 8. Attenuation (The "Fading Whisper")
* **Definition:** The loss of signal strength as it travels through a medium (wire or air).
* **CCNA Fact:** * **USB/Lightning:** High attenuation. Signals fail after ~15 feet.
    * **Ethernet:** Low attenuation. Reliable up to **100 meters (328 feet)**.
    * **Wi-Fi:** High attenuation through walls and interference from microwaves.

---

<a name="section-9"></a>
## 9. Operating Systems: The "Personalities"
Different OSs act as the "Security Guards" for your hardware.

| OS | Personality | Networking Behavior |
| :--- | :--- | :--- |
| **ChromeOS (Linux)** | The Scientist | Allows deep command-line control (TTL edits) but hides them behind "Developer Mode." |
| **Android** | The Tinkerer | Open enough to allow apps like NetShare to create "Side Roads" (Proxies). |
| **iOS (iPhone)** | The Guard | Very strict. It resets TTL headers and blocks hotspot toggles if the SIM plan is missing. |
| **Windows/Linux** | The Professional | Provides full control over Ethernet and Static IPs without "permission" from a carrier. |

---

<a name="section-10"></a>
## 10. The OSI Model Context (Theory)
When troubleshooting my "Digital Library," I'm moving through the **OSI (Open Systems Interconnect) Model**.

| Layer | Name | Your Lab Activity |
| :--- | :--- | :--- |
| **Layer 7** | Application | Running **Jellyfin**, **SSH**, or **Samba**. |
| **Layer 4** | Transport | Managing **Port Numbers** (e.g., SSH on Port 22, NetShare on 8282). |
| **Layer 3** | Network | Editing **TTL** values and assigning **IP Addresses**. |
| **Layer 2** | Data Link | Identifying devices by **MAC Address** via a Switch. |
| **Layer 1** | Physical | Comparing **Ethernet** vs. **USB** and managing **Attenuation**. |

---

<a name="section-11"></a>
## 11. Encapsulation: The "Envelope" Concept
Think of the data movement as a postal service. Each layer adds a new "wrapper" around the data.

1. **The Data:** My movie file (Jellyfin).
2. **The Segment (L4):** Chopping the movie into small pieces.
3. **The Packet (L3):** Putting the piece in an envelope with an **IP Address** and a **TTL** number. 
   * *Lab Note:* Changing the TTL to 65 is like "writing on the envelope" before the carrier sees it.
4. **The Frame (L2):** Putting that envelope in a delivery truck with a **MAC Address**.

---

<a name="section-12"></a>
## 12. DHCP vs. Static IP
In a network, devices need a way to get their "Name Tags" (IPs).

* **DHCP (Dynamic Host Configuration Protocol):** The "Librarian" (Router/Phone) automatically hands out addresses.
* **Static IP:** I manually assign a permanent address. 
   * **CCNA Best Practice:** Servers (Chromebook Library) should always use **Static IPs** so clients (iPad/iPhone) always know where to find them.

---

<a name="section-13"></a>
## 13. The Default Gateway (The "Exit Sign")
* **Definition:** The IP address of the device that leads to the "Outside World" (Internet).
* **In My Lab:**
   * My **Android Phone** acts as the Default Gateway.
   * If the Chromebook talks to the ThinkPad, it stays inside.
   * If the Chromebook talks to Google.com, it heads for the **Default Gateway**.

---

<a name="section-14"></a>
## 14. Connectivity Testing (ICMP)
* **Protocol:** **ICMP** (Internet Control Message Protocol).
* **The Tool:** `ping`.
* **The Goal:** Sending an "echo request" to see if a device is alive.
   * **Command:** `ping <Target_IP_Address>`
   * **Result:** If I see "64 bytes from...", Layer 3 connectivity is confirmed.

---

<a name="section-15"></a>
## 15. 🛠️ Troubleshooting Flowchart
Use this logic when the "Library" is down:
1. **Physical:** Is the cable plugged in? Is the Hotspot toggle on?
2. **Data Link:** Do I see a MAC address? Can I see the device in Bluetooth settings?
3. **Network:** Do I have an IP address? Can I **Ping** the gateway?
4. **Application:** Is the Jellyfin service actually running on the Chromebook?

---

<a name="glossary"></a>
## Glossary of CCNA Terms
To help you organize your Digital Library Syllabus, I've alphabetized your glossary and added a "Jump to Letter" navigation bar. I also filled in the missing definitions for the terms we've discussed today to make it a complete reference for your CCNA studies.

<a name="glossary"></a>

📖 Glossary of CCNA Terms
Jump to: A | D | E | F | G | H | I | L | M | N | P | R | S | T | W

<a name="g-A"></a>

A
** Access Point (AP)**: A device that creates a wireless local area network (WLAN). It acts as a bridge between wireless devices and a wired network.

**Attenuation**: The natural weakening of a signal (like Wi-Fi or electrical pulses in a wire) as it travels over a distance or through obstacles.

<a name="g-D"></a>

D
**Default Gateway**: The "Exit Sign" for my network. It is the IP address of the router that my devices use to send data outside of the local network.

**DHCP (Dynamic Host Configuration Protocol)**: The "Librarian" service that automatically assigns IP addresses to devices when they join a network.

<a name="g-E"></a>

E
**Encapsulation**: The process of "wrapping" data in different layers of headers (the envelope concept) as it moves down the OSI model.

**Ethernet**: The standard technology for wired local area networks. It uses cables (like Cat6) to provide fast, stable, Full-Duplex communication.

<a name="g-F"></a>

F
**Full-Duplex**: A communication mode where data can be sent and received at the exact same time (like a telephone conversation).

<a name="g-G"></a>

G
**Global Backbone**: The massive, high-speed fiber optic cables that connect continents and major ISPs to form the core of the Internet.

<a name="g-H"></a>

H
**Half-Duplex**: A communication mode where only one device can transmit at a time (like a walkie-talkie).

<a name="g-I"></a>

I
**ICMP (Internet Control Message Protocol)**: The protocol used for "error reporting" and testing connectivity. It is the engine behind the ping command.

**IP Address** : My temporary "Mailing Address." A logical address assigned by software to identify my device on a network.

<a name="g-L"></a>

L
**LAN (Local Area Network)**: My private "neighborhood" of devices inside my home or lab.

<a name="g-M"></a>

M
**MAC Address (Media Access Control)**: My permanent "Social Security Number" for my network card. A physical address burned into the hardware.

<a name="g-N"></a>

N
**NAT (Network Address Translation)**: Hiding many private IPs behind one single public IP address to save space and add security.

**Node**: Any single device connected to my network, whether it's a server, laptop, or phone.

<a name="g-P"></a>

P
**Packet**: The unit of data at Layer 3 (Network Layer) that contains the IP addresses and the TTL value.

<a name="g-R"></a>

R
**Router**: The "Border Guard" that connects two different networks (like my LAN to the Internet). It makes decisions based on IP addresses.

<a name="g-S"></a>

S
**Static IP**: An IP address that I manually assign to a device so it never changes (best for servers like my Jellyfin lab).

**Switch**: The "Internal Street Manager." It connects devices within a LAN and uses MAC addresses to send data to the right port.

<a name="g-T"></a>

T
**TTL (Time To Live)**: A value in the IP header that prevents packets from looping forever. It drops by 1 every time it hits a router.

<a name="g-W"></a>

W
**WAN (Wide Area Network)**: A large-scale network that connects multiple LANs. The Internet is the world's largest WAN.




