# offline-home-infrastructure
I created this project to explore architecture behind personal streaming platforms. By turning a Chromebook into a localized Linux server, I've created a private ecosystem for cross-platform media and file sharing. Come explore how I set this up!

# Key Idea

A **homelab** is simply using their own devices to experiment with networking, servers, and software.

Allegedly a small setup can teach:

* networking basics
* servers
* file sharing
* local services
* system administration

---

So I'll be using this to try to learn networking basics and hopefully help me get a better understaning of how it all comes together.


## Devices Inventory

| Version 1.1 | 
| Device | Role & Description |
| :--- | :--- |
| **iPhone** | **Temporary Network Access Point** – Used to create a local Wi-Fi network using Personal Hotspot. This allows devices to communicate locally even without internet access. Needs testing for stability with multiple devices. |
| **Android Phone** | **Testing Device** – Used to verify that services (such as Jellyfin) work across different operating systems and mobile platforms. |
| **Chromebook (Lenovo)** | **Primary Server** – Planned host for media services such as Jellyfin. Acts as the central location where the media library is stored and served to other devices on the network. |
| **Lenovo ThinkPad** | **Primary Workstation** – Used to manage the server, upload media files, and configure services. This device acts as the main administrative console. |
| **Windows Device** | **Secondary Client / Testing Machine** – Used to test compatibility with Windows-based systems and verify that network services are accessible across different operating systems. |
| **iPad** | **Mobile Streaming Endpoint** – Used to test media streaming and verify that Jellyfin services are accessible from tablet devices on the network. |



## Installations 

### **Network Services**
*These are processes that run throughout networks and provide remote interactive access, file transfer, and critical administration functions for my systems' operation.*

| Service | Purpose & Usage |
| :--- | :--- |
| **Samba** | Used for sharing files on a network to different operating systems. |
| **OpenSSH** | Used for remote management and secure terminal access (Linking IdeaThinkPad and Chromebook). |
| **Jellyfin** | Used as the Media endpoint for streaming content to clients. |


### **System Utilities**
*These are used to list or change information that is related to data sets and volumes, such as data set names, catalog entries, and volume labels. Think "Librarians Tools"*

| Utility | The Analogy (The Tool) | Practical Purpose |
| :--- | :--- | :--- |
| **Vim/Nano** | **The Pen & Paper** | Tools used to write the "Rulebooks" (Configuration files) that tell the staff how to behave. |
| **Net-tools** | **The Signpost & Clipboard** | Used to check the library's "Street Address" (IP Address) and verify that the "Roads" (Network) are clear of traffic and working properly. |

To see the commands I learned or used, see the [Commands](./Commands.md) file (leads to a separate page).
