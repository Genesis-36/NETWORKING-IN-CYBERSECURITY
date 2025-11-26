# Network Topologies & Security

---

## I. Logical vs Physical Topology

###  Logical Topology
This refers to **how data moves within the network**, based on security or operational needs.
It doesn't care where devices are physically located — it cares about **who can talk to whom**.
 Example:
* **VLANs (Virtual LANs)**: Separate employees from guests even if they are in the same building.
* **ACLs (Access Control Lists)**: Decide which devices are allowed to access servers, like allowing only managers to access payroll data.
 Purpose:
* Improve security by dividing the network
* Control who can access sensitive systems
* Manage network traffic better

---

###  Physical Topology
This refers to **how devices are physically connected**, based on their **location or building structure.**
 Example:
* New York Office LAN
* Headquarters LAN
These divisions make it easier to manage networks across different **branches or offices**.

---

## II. Types of Network Topologies
---

### 1️⃣ Bus Topology
 **Explanation:**
All devices are connected to a **single cable** (like a main road).
Data travels in **one direction**.
It is old, simple, and only used for **very small networks**.
 Advantages:
* Cheap and easy to set up
* Uses only one cable
 Disadvantages:
* If the main cable breaks — entire network fails (single point of failure)
* Slow when too many devices
* Only half-duplex (cannot send and receive at same time)

---

### 2️⃣ Star Topology
 **Explanation:**
All devices connect to **one central switch or hub** (like a teacher in the middle of a classroom).
Every computer talks through the central device.
 Advantages:
* Easy to manage and troubleshoot
* If one device fails, the rest still work
* Good performance
 Disadvantages:
* If the central switch fails, the whole network goes down
* More expensive (because of switch and cables)

---

### 3️⃣ Ring Topology
 **Explanation:**
Devices are connected in a **circle**.
Data moves from one device to another **in one direction**, until it reaches the destination.
 Advantages:
* Very few data collisions
* Good for networks with predictable traffic
 Disadvantages:
* If one device or cable fails — the whole network stops
* Not easy to add/remove devices
* Slower when more devices are added

---

### 4️⃣ Mesh Topology

 **Explanation:**
**Every device is connected to every other device.**
There are two types:
 Partial Mesh — Some devices are connected
 Full Mesh — All devices are connected
 Advantages:
* Very reliable (no single point of failure)
* Highly secure
 Disadvantages:
* Very expensive (lots of cables)
* Difficult to set up and maintain

---

### 5️⃣ Flat Networks

 **Explanation:**
All devices are on **one big network** — no segmentation.
Everything can talk to everything else.
 Example: Your home WiFi — your phone, TV, laptop, all connected together.
 Security Risk:
* If one device gets hacked, the attacker can reach everything easily.
* No protection between devices → Poor security

---

###  Segmented Networks

**Explanation:**
The network is **divided into smaller sections** (like separate rooms in a building).
You control **who can access what**.
Example:
* Guest WiFi (separate)
* Internal company WiFi
* IoT devices kept in a separate network
Advantages:
* Limits the spread of cyber-attacks
* Better security and management

---

## III. Network Topology & Security

Network topology affects **how a cyber attack spreads and how we respond to it.**
 Think of a ship:
If the ship is hit by water (attack), **segmented rooms** stop water from flooding the whole ship.
Just like that, **segmented networks** limit damage.
 Key Idea:
Modern security is not only about **stopping attacks**, but also **containing and minimizing damage.**

---

## IV. Mitigation Techniques

To improve network security, organizations can use:

| Technique          | Purpose                                  |
| ------------------ | ---------------------------------------- |
| VLANs              | Separate traffic into logical groups     |
| Firewalls          | Block unwanted connections               |
| ACLs               | Control who can access what              |
| Jump Boxes         | Secure remote access to internal systems |
| QoS Control        | Limit bandwidth for risky devices        |
| Internal Firewalls | Protect devices inside the network       |
| Segmentation       | Limit the impact of breaches             |

 Companies that use strong segmentation face **less damage during attacks**, recover faster, and often only lose **1–2 devices**, not the entire network.

---

## Final Summary (In Simple Words)

| Concept           | Meaning                                 |
| ----------------- | --------------------------------------- |
| Logical Topology  | How data moves                          |
| Physical Topology | How devices are physically connected    |
| Flat Network      | No segmentation (dangerous)             |
| Segmented Network | Divided for security                    |
| Mesh              | Most secure and reliable, but expensive |
| Star              | Most commonly used                      |
| Ring/Bus          | Old and less secure                     |
