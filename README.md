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
* Samba: used for sharing files on a network to different operating systems 
* OpenSSH: used for remote management and secure terminal access (Using Ideathinkpad and Chrome
*  Jellyfin: used for Media endpoint 
*  Net-tools: used for essential networking commands like ifconfig and netstat
*  Nano/Vim: used for editing configuration files in the Linux terminal
