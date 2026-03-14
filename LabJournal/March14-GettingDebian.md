### The ThinkPad Transition (Windows to Debian)
---

Okay, I finally got my USB in the mail so I decided to finally install Linux onto the laptop my cousin didn't want anymore.
I started trying to figure it out last night—what I needed to make the Lenovo Windows change into a Linux OS. It was overwhelming
looking at all these different links. Eventually, I gave up and used Gemini to help me install stuff and learn different things
that came up in the download.

At first, I thought downloading an ISO would be enough, and then restarting the Lenovo (WHICH TOOK FOREVER BY THE WAY. I kept having to
figure out how to properly restart it. I knew I could find the BIOS, but it turns out I just needed to hold shift down while pressing 
Fn + F12. 
Only took three hours to learn this) and binga booma it's done!

But after some trial and error, I learned I actually needed what I called a "translator" (using Rufus) that actually turns the ISO 
(which is more like "code") and gets it translated into a proper working Operating System. Gemini was a HUGE help. I made the decisions
myself, but I would ask Gemini why someone might want one choice over another.

## **Why Debian?**
--
I decided to use Debian because I heard lots of great things about using this to get hands-on with servers and learn hands-on. I also debated 
about using Ubuntu instead since I've used that before in classes. I decided I wanted to try to challenge myself and expand my usage of Linux. 
A lot of the reading and videos I watched talked about how Debian was more "heavy" to use, so I figured I'd try to give that a good start. I
also had a feeling I could learn a lot using this platform.

So I changed the Lenovo from a Windows server to a Debian server, but I will admit I cheaped out and got the GUI instead of choosing to run it 
in the kernel and terminal. Once it downloaded (cough One day and five hours later cough cough) I got so excited about it I started browsing
around the laptop instead of getting right to getting everything I needed for the homelab up and running.

## **First Impressions**
--
Something that surprised me was that I actually loved the GUI more than I thought. I will admit it does feel more like a tablet than an actual 
laptop so it'll probably take some adjustment, but I'm okay with it. The main hangup I'm having is for some reason I'm having difficulty closing 
Firefox, the app store, and any other services I open. I did notice scrolling was significantly faster, especially for scrolling on Firefox. 
I was shocked by how fast that was. But it was good. Uninstalling games and some apps were also surprisingly fast to get rid of too, which was WILD.

## **Helpful Links**
--
[The Art of using Linux, and why YOU should too By: diinki](https://www.youtube.com/watch?v=z4iSZetVkRg&list=PL0MIQt2UqdYpwdReoJ9h8-cVaOvvGm7kQ&index=78) **opens in a new page**
[10 Things To Know About DEBIAN Linux By:The Linux Cast](https://www.youtube.com/watch?v=bUykbKO3JiA&list=LL&index=4&t=454s) **opens in a new tab**
[How to (actually) learn Linux By: Bread on Penguins](https://www.youtube.com/watch?v=j-Ha0vl-0ME&list=LL&index=7) **opens in a new tab**
[Ubuntu 22.04 LTS Vs Debian 12 | This FINALLY Made Me Switch! By: Linux Tex](https://www.youtube.com/watch?v=O1V5zBDnHSY&t=261s) **opens in a new tab**


## **_The Quick Glossary_**
--
**ISO**: A single file that acts as a "blueprint" or "clone" of an entire operating system disk.

**GUI (Graphical User Interface)**: The visible things you see when you first log into your laptop.

**Kernel**: The "brain" of the OS that talks directly to the hardware.

**Terminal**: The text-based window where you type commands to talk to the Kernel.

**Root**: The "God Mode" account that has permission to change anything.

**Sudo**: Short for "SuperUser Do"—asking for temporary permission to do an admin task.

**Mounting**: The process of "opening" a drive so the OS can see the files inside.

# **Programs I Learned About** 
--
**Cockpit**: A web dashboard that lets me manage my Linux laptop from my Windows PC or Chromebook. Which sounds *AMAZING*

****lsblk*****: The command used to "list block devices" (to find where the USB is hiding).

**Handbrake**: A tool for "ripping" and shrinking DVDs so they fit on a hard drive.

**Jellyfin**: A media server (like a private Netflix) I'm building for movies and bonus features.

## The Roadmap For Linux Lenovo (Getting the Lab Ready)
-- Prepare the Server: Install Cockpit and find my IP address.

-- Remote Access: Log in to the ThinkPad from my Windows PC or Chromebook via Port 9090.

-- Media Pipeline: Set up Handbrake and Docker to prepare for my DVD library down the line. 

-- Networking Practice: Set a Static IP and use Wireshark to watch the network in real-time.

Random Thought:
---
I also kind of want to use Ubuntu, but I think I'll leave my other Lenovo to stay a Windows for now. Though I wouldn't be surprised if I change my mind.
Nothing is really set in stone as I’m still trying to figure out how to adapt everything. But I figured that I wanted to see if I could figure out how
to use a Windows OS, Chromebook OS, Linux, and Apple device all together. I think it'll help for it to be diversified so I can learn how to navigate the 
network on different platforms and how it works on each device. I don't know what I'm going to use in the future, so might as well get as hands-on as I 
can right?

I'm really looking forward to everything coming together. I'm getting excited about learning all of this and can't wait till I can learn and actually understand more!

I am a little nervous about how to burn DVDs. I don't doubt I can figure out how to get the movie to download, but I do worry about getting the SUBTITLES to download
with the video files. I'm using gemini to help and I think we've come up with a plan, but we shall see what happens! I beleive I'll figure it out some way some how,
I just need to be patient about the whole process first. But I think the setting up the laptops are comming along really well!

AAANd its late so I should probably go to bed soon. So Tata for now!
