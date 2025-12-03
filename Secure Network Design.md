## **Summary of Secure Network Design Concepts**
**I. Introduction**
A well-designed network protects confidentiality, integrity, and availability. Understanding network weaknesses helps improve resiliency and security.
---

## II. Secure Network Designs**
A secure network avoids:
* Single points of failure
* Over-complex dependencies
* Poor documentation
* Flat networks that allow lateral movement
* Over-reliance on perimeter defenses
Cisco SAFE architecture helps map protections across the campus, data center, cloud, Internet edge, and WAN.
---

## III. Business Workflows & Architecture**
Network layout should support workflows like email. Components (client, mailbox server, mail transfer server) should be placed in separate secure segments with controlled data flows.
---

## IV. Network Appliances**
* **Switches** – Layer 2 forwarding
* **Access Points** – Wireless bridging
* **Routers** – Layer 3 forwarding
* **Firewalls** – Traffic filtering
* **Load Balancers** – Distribute traffic
* **DNS Servers** – Name resolution
Using the OSI model simplifies network design and troubleshooting.
---

## V. Routing & Switching Protocols**
* **Layer 2:** MAC addressing, ARP, switching
* **Layer 3:** IP addressing, routing
  Common routing protocols: **BGP, OSPF, EIGRP, RIP**
--

## VI. Network Segmentation**
Segments reduce attack surfaces. VLANs provide logical Layer 2 segmentation; routers/firewalls enforce Layer 3 separation.
---

## VII. Network Topology & Zones**
Zones improve security by grouping hosts with similar trust levels:
* Intranet
* Extranet
* Guest/Internet
Traffic between zones must pass through controlled points (usually firewalls).
---

## VIII. Demilitarized Zones (DMZs)**
DMZs host **Internet-facing services** (web, email, proxies, VPN).
Hosts in the DMZ (“bastion hosts”) run minimal services and hold no sensitive data.
Common DMZ types include:
* Proxy DMZ
* Communication servers DMZ
* VPN DMZ
* Cloud access DMZ
* Multi-tier DMZ

Topologies:
* Screened subnet (two firewalls)
* Triple-homed firewall
* Screened host (less secure)
IPv6 must also be secured to avoid bypass attacks.
---

## IX. Routing & Layer 2 Attack Protection**
Threats include:
* Man-in-the-middle
* MAC cloning
* ARP poisoning
* MAC flooding
Mitigations: ARP security, port security, DHCP snooping, Dynamic ARP Inspection (DAI).
---

### X. Loop Prevention (STP)**
Spanning Tree Protocol prevents broadcast storms and loops.
BPDU Guard protects against rogue switches.
---

### XI. Physical Port Security**
* Lock physical access
* MAC filtering/limiting
* DHCP Snooping
* DAI (Dynamic ARP Inspection)
---

## *XII. Network Access Control (NAC)**
Verifies device compliance before granting access.
Includes:
* 802.1X authentication
* Health posture checks
* Persistent/nonpersistent agents
* Agentless options
---

## XIII. Route Security**
Attacks:
* Route injection
* Source routing abuse
* Router OS exploits
Defenses: authentication, route filtering, patching.
--

## XIV–XV. Wireless Security & WAP Management**
Secure wireless requires:
* Proper placement & channel planning
* Site surveys / heat maps
* WPA3 adoption
* Avoid WPS; use DPP (Easy Connect)
* Captive portals for guest access
* Enterprise authentication: 802.1X + EAP
* EAP methods: EAP-TLS, PEAP, EAP-TTLS, EAP-FAST
