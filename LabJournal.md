# Implementation Log: Project Digital Library
**Date:** March 3, 2026

## Status
**Phase 1 (Foundation & Documentation) Complete**

---

## Work Completed

### 1. Documentation Infrastructure (The "Syllabus")

- **Task:** Established a structured `Syllabus.md` to serve as a centralized study guide.
- **Result:** Created a 15-section roadmap covering everything from Layer 1 Physical physics to Layer 7 Application services.
- **CCNA Skill:** Developed technical writing and network topology documentation skills, essential for network audits.

---

### 2. Service Deployment (Jellyfin)

- **Task:** Installed and initialized the Jellyfin Media Server within the Linux container (Crostini).
- **Result:** Verified server-side readiness for local intranet streaming.
- **Learning:** Understood how a server listens on specific Ports (Layer 4) to provide services to clients.

---

### 3. Network Evasion & Traffic Engineering

- **Task:** Investigated carrier-level hotspot restrictions and implemented bypasses.

**Key Actions:**

- Tested NetShare (Proxy) to tunnel traffic past carrier entitlement checks.
- Mastered TTL (Time To Live) Manipulation to disguise tethered packets.
- Explored Direct Peer-to-Peer links (USB/Ethernet) to eliminate dependency on external gateways.

---

### 4. Security Hardening

- **Task:** Moved away from insecure password-based authentication.
- **Result:** Configured SSH Key-Pairs (ED25519).
- **Learning:** Practiced Asymmetric Encryption, ensuring the "Library" is only accessible by the authorized "Librarian" (ThinkPad).

---

### 5. Hardware Theory & Physics

- **Task:** Analyzed the physical limitations of the lab hardware.

**Key Concepts Learned:**

- **Attenuation:** Why long USB cables fail but Ethernet thrives.
- **Full-Duplex vs. Half-Duplex:** Why wired connections feel "snappier" than Wi-Fi.
- **OS Constraints:** How iOS, Android, and ChromeOS act as "Security Guards" for the network.

---

## Key Lessons Learned

- **The "Invisible" Network:** A network doesn't need "The Internet" to be functional; a local intranet is often faster and more secure for media sharing.
- **Packet Anatomy:** Small changes in a packet header (like TTL) can have massive real-world effects on connectivity.
- **Stability over Convenience:** Wired infrastructure (Ethernet/USB) is always superior to wireless for high-bandwidth tasks like streaming.

---

## Next Steps

- Perform a Connectivity Audit (Ping test) between all four devices.
- Map out the Static IP addresses for the server and management station.
- Stress-test the Jellyfin stream over the NetShare proxy.
