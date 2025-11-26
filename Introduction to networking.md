## I. What is Data Networking?

Imagine you have a phone and your friend has a phone. You want to send a message, picture, or video — how does it travel?
**Data Networking** is the technology that lets **computers and devices connect, communicate, and share data** with each other.

It's like building **roads for information** to travel — so emails, videos, WhatsApp messages, and websites can reach you.

 **Internet = a huge network of many small networks connected together.**
These small networks are of different sizes: **PAN, LAN, MAN, and WAN**.

---

## II. Types of Networks

### 1️⃣ PAN — Personal Area Network

 **Range**: Very small (1–10 meters)
 Devices: Phone, smartwatch, Bluetooth speaker, printer, earbuds

**Simple Example:**
When your phone connects to your AirPods or Bluetooth speaker — that’s a PAN.

 Technologies used: **Bluetooth, USB, Wi-Fi (small area)**

---

### 2️⃣ LAN — Local Area Network

 **Range**: Small area (home, school, office, 1–5 km)
 Devices: Computers, printers, routers, scanners in a building

**Simple Example:**
Your school computer lab or home Wi-Fi network is a **LAN**.

 Technologies: **Ethernet cables, Wi-Fi**
 Speeds: **Fast**, less congestion, cheaper to maintain

---

### 3️⃣ MAN — Metropolitan Area Network

 **Range**: A **city or large town** (40–60 km)
 Used to connect many LANs in a city.

**Simple Example:**
Banks connecting multiple branches *within a city.*
University campus connecting different buildings.

 Uses **Fiber Optic cables (backbone lines)** for speed.

---

### 4️⃣ WAN — Wide Area Network

 **Range**: Very large — **country, continent, or worldwide (100–1000 km+)**
 Connects LANs across states or countries.

**Simple Example:**
The **Internet** itself is the largest **WAN**.

 Uses **satellites, microwave links, submarine cables, routers, firewalls**
 Slower, expensive, harder to maintain.

---

###  LAN vs MAN vs WAN — Simple Comparison

| Feature      | PAN               | LAN                | MAN               | WAN             |
| ------------ | ----------------- | ------------------ | ----------------- | --------------- |
| Area Covered | Few meters        | Building or campus | City              | Country / World |
| Speed        | High              | High               | Moderate          | Low             |
| Ownership    | Personal          | Private            | Private/Public    | Public          |
| Example      | Bluetooth speaker | School Wi-Fi       | City bank network | Internet        |

---

---

# OSI MODEL — The 7 Layers Explained Simply

Think of sending a letter to someone:

* You write it
* Translate it (if needed)
* Put it in an envelope
* Add address
* Drop it at post office
* Transport it
* Delivery at destination

**Similarly, in networking, data goes through 7 layers**.

These 7 layers help us understand **how data moves from one device to another**.

---

##  The 7 Layers (Top → Bottom)

| Layer No. | Name         | Example                 |
| --------- | ------------ | ----------------------- |
| 7         | Application  | WhatsApp, Gmail, Chrome |
| 6         | Presentation | Encryption, Compression |
| 5         | Session      | Start/End connection    |
| 4         | Transport    | TCP, UDP                |
| 3         | Network      | IP, Routing             |
| 2         | Data Link    | MAC address, switches   |
| 1         | Physical     | Cables, signals         |

---

### 🔹 Layer 7 — Application Layer

* Closest to the **user**
* Gives interface for sending messages, browsing websites, email, etc.
* Uses **HTTP, SMTP, FTP**

 Example: When you send a WhatsApp message — this layer prepares it.

---

### 🔹 Layer 6 — Presentation Layer

* **Translates, encrypts, and compresses data**

 Example:

* Encrypts your WhatsApp message (so others can't read it)
* Converts picture formats (JPEG, MP4)

---

### 🔹 Layer 5 — Session Layer

* **Opens, manages, and closes communication**
* Keeps track — so if connection breaks, it continues from where it stopped.

 Example:
Downloading a file — breaks at 90% — resumes instead of starting from 0.

---

### 🔹 Layer 4 — Transport Layer

* **Ensures reliable delivery**
* Splits data into **segments**
* Uses **TCP (reliable)** and **UDP (fast but no guarantee)**
* Controls **speed and retransmission**

 Example:

* TCP used for emails, file transfers
* UDP used for video calling, gaming (fast, ignores some lost data)

---

### 🔹 Layer 3 — Network Layer

* **Finds the best path (routing) using IP addresses**
* Breaks data into **packets**

 Example:
IP address: 192.168.1.1 → identifies the destination network

---

### 🔹 Layer 2 — Data Link Layer

* Transfers data **within the same network**
* Uses **MAC addresses**
* Breaks packets into **frames**

 Example:
Your Wi-Fi router uses MAC addresses to send data to the correct device.

---

### 🔹 Layer 1 — Physical Layer

* Actual hardware: **cables, switches, radio signals, electricity**
* Converts data into **0s and 1s (bits)**

 Example:
Wi-Fi signals, fiber optic light pulses, Ethernet cables.

---

---

#  IP Addressing — Explained Simply

An **IP address** is like your **house address** on the internet.
It tells **where data should go and where it came from**.

Example IP address: `192.168.1.10`

 IP addresses have **4 numbers** (called octets), each from **0–255**.
Example: `192 . 168 . 1 . 10`

---

##  IP Address Classes

| Class | Range                       | Who uses it?                            |
| ----- | --------------------------- | --------------------------------------- |
| A     | 1.0.0.1 – 126.255.255.254   | Very large networks (Google, Microsoft) |
| B     | 128.1.0.1 – 191.255.255.254 | Medium-sized networks (Universities)    |
| C     | 192.0.1.1 – 223.255.254.254 | Small networks (Homes, offices)         |
| D     | 224.0.0.0 – 239.255.255.255 | Multicast                               |
| E     | 240.0.0.0 – 255.255.255.254 | Experimental                            |

---

##  Network Mask (Subnet Mask)

A subnet mask helps **separate the Network ID and Host ID**.

Example:
IP: `192.168.1.10`
Subnet Mask: `255.255.255.0`

| Part | Explanation            |
| ---- | ---------------------- |
| 255s | Network part — fixed   |
| 0s   | Host part — can change |

 So all devices in `192.168.1.***` are in the same network.

---

---

##  Subnetting — Explained Like a Teacher

Imagine you have a school with **100 students**, and I want to group them into **4 classes**.

Instead of **one large network**, we divide it into **smaller sub-networks** (subnets).

Example:

IP: `192.168.1.0`
Mask: `255.255.255.240` → gives 16 addresses per subnet.

| Subnet No. | Network Address | Usable IPs | Broadcast Address |
| ---------- | --------------- | ---------- | ----------------- |
| 1          | 192.168.1.0     | .1 – .14   | .15               |
| 2          | 192.168.1.16    | .17 – .30  | .31               |
| 3          | 192.168.1.32    | .33 – .46  | .47               |

 Each subnet acts as a mini-network.
Useful in schools, hotels, offices, organizations, etc.

---

---

# Final Quick Summary

| Topic  | Simple Meaning                          |
| ------ | --------------------------------------- |
| PAN    | Bluetooth-based small network           |
| LAN    | Home, school, or small office network   |
| MAN    | Network for a city                      |
| WAN    | Global network — like the Internet      |
| OSI    | 7 layers explaining how data travels    |
| IP     | Address of your device on a network     |
