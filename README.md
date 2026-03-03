# offline-home-infrastructure
I created this project to explore architecture behind personal streaming platforms. By turning a Chromebook into a localized Linux server, I've created a private ecosystem for cross-platform media and file sharing. Come explore how I set this up!


## Devices Inventory

| Device | Role & Description |
| :--- | :--- |
| **Android Phone** | The bridge for the networking devices. |
| **Chromebook Lenovo** | **Primary Server** - Central host for Media services. |
| **Lenovo IdeaThinkPad** | **Primary Workstation** - Used to manage the console and primary file uploader. |
| **iPad** | Mobile streaming endpoint for verifying Jellyfin services. |

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


To see the commands I learned or used see "Commands" file
