#  Network Reconnaissance Tools 
---
##  What is Network Reconnaissance?
**Network Reconnaissance** means *collecting information about a network to understand how it is built, which devices exist, and what services are running.*
Think of it like a **map maker exploring a city** — identifying streets, buildings, and important locations.
 Used by:
*  Security professionals (to protect networks)
*  Hackers (to find weak points)

---

# I. Basic Tools: IPCONFIG, PING, ARP

###  1. ipconfig / ifconfig — (Who am I?)
Shows **your computer’s own network identity**, including:
* IP address
* MAC address
* Default gateway
* Whether you use DHCP (automatic IP assignment)
Think of it like checking your **home address and phone number**.

---

###  2. ping — (Are you alive?)
Ping tests **whether another device is reachable** on the network.
Example: `ping google.com`
If it replies — the device is **online and reachable**.
 Like shouting someone’s name to check if they are there and can hear you.

---

### 3. arp — (Who's at this IP?)
ARP shows **which IP addresses are linked to which MAC addresses** in your local network.
 Useful for detecting **spoofing or Man-in-the-Middle attacks**, where someone pretends to be the router.
It's like checking if someone is **lying about their identity**.

---

#  II. ROUTE and TRACEROUTE — (Which Path Does the Data Travel?)

###  1. route
Shows **how your computer chooses which path (gateway) to use to send data**.
If strange entries exist, it could indicate malicious routing.
---
###  2. tracert / traceroute
Shows **all the stops (hops) your data makes** before reaching the destination.
Example: tracert google.com
It will show all routers your signal passes on the way.
 Like tracking the path of a letter through **post offices before it gets delivered**.
---
###  3. pathping / mtr
Mixes **ping and traceroute**, showing **packet loss and delay** on each hop.
 Helps detect congestion or attacks like denial-of-service (DoS).
---

# III. IP Scanners & Nmap — (Smart Network Scanning)
**Ping scanning is slow and basic**.
Advanced tools like **Nmap** are used for **faster and smarter scanning**.
###  What Nmap Can Do:
| Feature           | Meaning                                   |
| ----------------- | ----------------------------------------- |
| Host discovery    | Find active devices                       |
| Port scanning     | Find open doors (ports)                   |
| OS detection      | Guess operating system                    |
| Service detection | Identify software running                 |
| Stealth scanning  | Sneaky scanning without triggering alarms |

Example basic scan:
nmap 192.168.1.0/24
```
 Nmap can **scan a whole neighborhood**, not just one house like ping.
---

#  IV. Service Discovery & Fingerprinting with Nmap
After scanning devices, we want to know:
| What to discover        | Why it's important                   |
| ----------------------- | ------------------------------------ |
| Which OS they run       | Helps find vulnerabilities           |
| Which services are open | Detect risky services                |
| Which software version  | Check if it’s outdated or vulnerable |

### Common Nmap Flags:
| Flag | Purpose                            |
| ---- | ---------------------------------- |
| -sS  | Stealth TCP SYN scan               |
| -sU  | UDP scan                           |
| -p   | Choose port range                  |
| -sV  | Detect service version             |
| -O   | Detect operating system            |
| -A   | Full scan (OS + version + scripts) |

Service fingerprinting is like **recognizing someone by their voice, face, and habits**.

---

# V. netstat and nslookup
### 1. netstat
Shows **active connections and open ports** on your own computer.
Useful for:
 Detecting malware
 Finding unauthorized open services (e.g., hidden FTP, web servers)
It answers: **Who is my system talking to?**
---
### 2. nslookup / dig
Used to **query DNS** and find:
* Domain → IP
* Mail servers
* Name servers
Example:
nslookup google.com
```
Useful for detecting **DNS misconfigurations**, like *zone transfers*, which can reveal the full network.
---

# VI. Advanced Reconnaissance Tools
| Tool         | Use Case                                   |
| ------------ | ------------------------------------------ |
| theHarvester | Collect emails, names, subdomains (OSINT)  |
| dnsenum      | Scan DNS records and IP ranges             |
| scanless     | Anonymous online port scanning             |
| curl         | Test web applications (GET, POST requests) |
| Nessus       | Automatic vulnerability scans              |
---

### Example: theHarvester
Collects emails, subdomains, and staff names online.
```
theHarvester -d example.com -b google
```
 Great for **social engineering and phishing risk assessment**.
---

###Nessus — Vulnerability Scanner
Cross-checks software versions with known vulnerabilities (CVE database).
Used by security professionals and penetration testers.
Like a **doctor scanning the body for diseases**.

---

#Final Summary
| Tool               | Purpose                           |
| ------------------ | --------------------------------- |
| ipconfig/ifconfig  | View own IP details               |
| ping               | Test connectivity (alive or not)  |
| arp                | View IP-to-MAC mapping            |
| route              | Check routing paths               |
| traceroute/tracert | Map the path to destination       |
| Nmap               | Scan devices, ports, services, OS |
| netstat            | Show open connections and ports   |
| nslookup/dig       | Query DNS records                 |
| Nessus             | Scan for vulnerabilities          |
| theHarvester       | Collect OSINT information         |
