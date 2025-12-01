# I. PACKET CAPTURE & TCPDUMP**

## **What is Packet Capture?**
Think of your network like a highway.
Every message going through the network is a “car,” and each car carries data.
**Packet capture** means taking pictures of those cars as they pass, so you can inspect what’s inside.
---

### **Packet Analysis vs Protocol Analysis**
**Packet Analysis:**
  You look at each packet (car) one-by-one in **detail**.
  Example: Checking every item inside a car’s trunk.

**Protocol Analysis:**
  You look at **patterns** in many packets at once.
  Example: Counting how many cars go through a toll gate in 1 hour.
---

### **How Do You Capture Packets?**
You Need a **sniffer** like tcpdump or Wireshark
There are 2 ways to capture traffic:
1. **From a host** → Only captures traffic going to/from that device.
   Like standing inside one room and listening only to sounds in that room.
2. **From the network segment** → Captures all traffic on a path.
   Done using:
   * **SPAN/Mirror Port:** The switch copies traffic for you.
   * **TAP:** A device physically placed on the cable to copy traffic.
---

###  **Where Do You Place a Sniffer?**
Usually:
* Inside the firewall
* Near important servers
Because you're trying to catch **malicious traffic that slipped through**.
But careful: one sniffer can gather **huge** amounts of data, so you can’t put them everywhere.
---

# **TCPDUMP (Linux Packet Capture Tool)**
### Basic Command:
tcpdump -i eth0
This listens on the **eth0** network interface and shows packets live.

### ✔ Save to a file:
tcpdump -i eth0 -w capture.pcap
### ✔ Read a saved file:
tcpdump -r capture.pcap
---

## **Filters in tcpdump**
To avoid capturing too much traffic, you use filters:

### Types of Filters:
1. **Type** → host, net, port
2. **Direction** → src, dst
3. **Protocol** → tcp, udp, arp, icmp

### Boolean Operators:
* `and`
* `or`
* `not`

### Example Filter:
Capture frames **only** from source IP `10.1.0.100` going to **port 53 or 80**:
tcpdump -i eth0 "src host 10.1.0.100 and (dst port 53 or dst port 80)"
---

# **II. PACKET ANALYSIS & WIRESHARK**
###  What is Wireshark?
Wireshark is a **GUI tool** (graphical tool) that lets you see packets in a friendly interface.
When you open Wireshark, you see a **3-pane window**:
1. **Packet List Pane**
   All packets captured.
2. **Packet Details Pane**
   Breakdown of the selected packet (layer by layer).
3. **Packet Bytes Pane**
   Raw data in hex/ASCII.
---

### Wireshark Features
* Can decode **hundreds of protocols**.
* Can read or save **.pcap / .pcapng** files.
* Has **capture filters** (like tcpdump).
* Has **display filters** (very powerful).
* Color coding makes it easier to spot issues.

### Follow TCP Stream
This lets you reconstruct a conversation, like reading a full chat between a client and server.
---

# **III. PACKET INJECTION & REPLAY**
Sometimes you don’t just capture packets — you **send fake or crafted packets** for testing.
Tools used for this:
* **hping**
* **Scapy**
* **Ettercap**
* **Dsniff**
---

# � **1. hping**
hping lets you create custom packets.
### What can you do with hping?
####  Host/Port Detection
Like Nmap — find open ports.

#### ✔ Firewall Testing
See what traffic gets blocked or allowed.
#### ✔ Traceroute Alternatives
If ICMP is blocked, hping can trace using TCP/UDP.
#### ✔ DoS Attack Tests
Example: Flood a server with SYN packets to test its resilience
---

#  **2. tcpreplay**
This tool takes a saved **.pcap file** and replays it onto the network.
### Why use tcpreplay?
* Test IDS/IPS rules
* Reproduce suspicious traffic
* Train analysts
Example: You replay a captured attack to check whether your firewall detects it.
---

#  **3. Netcat (nc)**
Netcat is like the **Swiss army knife of networking**.
### ✔ Check open ports:
echo "head" | nc 10.1.0.1 -v 80
### ✔ Create a backdoor:
On victim:
nc -l -p 666 -e cmd.exe
---

#  **NETWORK ATTACK EXAMPLES**

## **A. Man-in-the-Middle (ARP Spoofing)**
### Steps:
1. **Install Ettercap**
sudo apt update && sudo apt install ettercap-text-only
sudo ettercap -G
2. **Choose victim IP + gateway**
3. **Start ARP spoofing**
   Your machine becomes the "middle man."
4. **Open Wireshark**
   Capture and inspect data passing through you.

## **B. DoS Attack Example (Training ONLY)**
sudo hping3 -S --flood -V -p 80 192.168.1.100
This sends thousands of SYN packets per second to overwhelm the target.
---

**SUMMARY
###  Packet capture = recording network traffic
### tcpdump = command-line capture tool
### Wireshark = GUI analyzer
### Filters = help shrink overwhelming data
### Injection tools (hping, Scapy) = send custom packets
### Replay tools (tcpreplay) = repeat captured attacks
### Netcat = simple tool for scanning, file transfer, backdoors
### ARP spoofing = intercept traffic
### DoS = overwhelm a target with traffic
