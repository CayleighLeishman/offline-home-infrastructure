# **Quick Summary**

| Situation              | Method               |
| ---------------------- | -------------------- |
| Family in my house     | Private IP + `:8096` |
| Family outside         | Port forwarding      |
| More secure sharing    | VPN / Tailscale      |
| Advanced homelab setup | Reverse proxy        

---

# Jellyfin Media Sharing Cheat Sheet (My Setup)

When I want to send my media to family, there are **two main paths** depending on where they are.

* **Inside my house → LAN**
* **Outside my house → WAN / Internet**

---

# 1. Sharing Inside My House (LAN Path)

If family is **connected to my home network**, this is the easiest setup.
They **don’t need the internet** to reach my server.

### How they connect

1. Open the Jellyfin app **or** a web browser.
2. Type my **private IP address** followed by the port.

Example:

```
192.168.1.25:8096
```

### What this means

* The media stays **inside my network**
* It's **very fast**
* It **does NOT use my internet data**

Basically, their device is just **talking directly to my Linux laptop** on the same network.

---

# 2. Sharing Outside My House (WAN Path)

If family lives somewhere else, my **home network has to connect to the internet** so they can reach my server.

There are **three main ways** to do this.

---

# Option A — Port Forwarding

*(The “Open Door” method)*

I configure my **router** to send Jellyfin traffic to my laptop.

### How it works

If someone connects to my **public IP** on the Jellyfin port, the router sends them to my server.

Example idea:

```
Internet → Router → Jellyfin Server
```

### Pros

* Simple
* Easy for family to access

### Cons

* Less secure if done wrong
* It exposes my server to the internet

---

# Option B — VPN (Tailscale)

*(The “Secret Tunnel” method)*

Instead of opening my network, I create a **private tunnel**.

Everyone installs a small app like:

* Tailscale

### How it works

Their phone/computer behaves **like it's on my home network**, even if they are miles away.

So they connect exactly like LAN.

Example:

```
Family device → Tailscale tunnel → My server
```

### Pros

* Extremely secure
* My server is not exposed to the internet

### Cons

* Everyone needs the VPN app installed

---

# Option C — Reverse Proxy

*(The “Professional / Homelab” method)*

I run a program that sits **in front of Jellyfin** and manages connections.

Common tools:

* Caddy
* Nginx

### How it works

Instead of typing an IP, family uses a **domain name**.

Example:

```
family.cayleigh.com
```

The proxy:

1. Checks the connection
2. Adds encryption (SSL)
3. Sends the request to Jellyfin

### Pros

* More professional
* Secure HTTPS connection
* Works like normal websites

### Cons

* More complicated to set up

---

# 3. Creating Family Accounts in Jellyfin

Even if everyone connects, I **don’t want them using my account**.

So I create **separate users** in the Jellyfin dashboard.

Using:

* Jellyfin

### Why this helps

**Individual profiles**

* Mom
* Dad
* Siblings

Everyone gets their own login.

### Benefits

**Separate watch history**

* My "Recently Watched" stays clean

**Parental controls**

* Restrict folders like:

  * Kids → Cartoons only

**Download / Sync**

* Family can download movies to their phone before traveling

---

# Important Note: Upload Speed

When streaming **outside my house**, the limiting factor is my **internet upload speed**.

If upload is slow:

* movies may **buffer**
* video may **lower quality**

This is where **transcoding** helps.

Transcoding = Jellyfin **shrinks the video** so it streams easier.

---

**Notes from Gemini and rephrased by Chatgbt** 
