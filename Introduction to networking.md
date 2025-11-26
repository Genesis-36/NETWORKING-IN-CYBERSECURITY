I. Logical Topology

Network segmentation based on operational or security requirements helps optimize performance and ensure the protection of sensitive resources. By using techniques such as VLANs (Virtual Local Area Networks) and ACLs (Access Control Lists), organizations can control traffic flow and restrict access to critical systems effectively.

Based on operational or security requirements.
Typically achieved through the use of VLANs and/or ACLs.
Examples:
Network device management VLAN.
Database server VLAN.


II. Physical Topology

To efficiently organize and manage network infrastructure, it's common to segment networks based on geographic location or office structure.

These segments are often divided by office or branch, enabling better administration and resource allocation.
Examples include:
New York LAN
Headquarters LAN
This approach helps streamline communication, enhance security, and simplify troubleshooting across distributed environments.


1. Bus Network Topology



Network topology is the description of the arrangement of nodes (e.g. networking switches and routers) and connections in a network, often represented as a graph.

Bus topology is a network type where every device is connected to a single cable that runs from one end of the network to the other. This type of network topology is often referred to as line topology. In a bus topology, data is transmitted in one direction only. If the bus topology has two endpoints then it is referred to as a linear bus topology. Smaller networks with this type of topology use a coaxial or RJ45 cable to link devices together. However, the bus topology layout is outdated and you’re unlikely to encounter a company using a bus topology today.

Advantages

Bus topologies were often used in smaller networks. One of the main reasons is that they keep the layout simple. All devices are connected to a single cable so you don’t need to manage a complex topological setup. The layout also helped make bus topologies cost-effective because they can be run with a single cable. In the event that more devices need to be added then you could simply join your cable to another cable.

Disadvantages

However, relying on one cable does mean that bus topologies have a single point of failure. If the cable fails then the entire network will go down. A cable failure would cost organizations a lot of time while they attempt to resume service. Further to this, high network traffic would decrease network performance because all the data travels through one cable. This limitation makes bus topologies suitable only for smaller networks. The primary reason is that the more network nodes you have, the slower your transmission speeds are going to be. It is also worth noting that bus topologies are limited in the sense that they are half-duplex, which means that data can’t be transmitted in two opposite directions simultaneously.

2. Star Network Topology



A star topology is a topology where every node in the network is connected to one central switch. Every device in the network is directly connected to the switch and indirectly connected to every other node. The relationship between these elements is that the central network hub is a server and other devices are treated as clients. The central node has the responsibility of managing data transmissions across the whole network and acts as a repeater. With star topologies, computers are connected with a coaxial cable, twisted pair, or optical fiber cable.

Advantages

Star topologies are most commonly-used because you can manage the entire network from one location: the central switch. As a consequence, if a node that isn’t the central node goes down then the network will remain up. This gives star topologies a layer of protection against failures that aren’t always present with other topology setups. Likewise, you can add new computers without having to take the network offline like you would have to do with a ring topology.

In terms of physical network structure, star topologies require fewer cables than other topology types. This makes them simple to set up and manage over the long-term. The simplicity of the overall network design makes it much easier for administrators to run troubleshooting when dealing with network performance faults.

Disadvantages

Though star topologies may be relatively safe from failure, if the central switch goes down then the entire network will go down. As such, the administrator needs to manage the health of the central node closely to make sure that it doesn’t go down. The performance of the network is also tied to the central node’s configurations and performance. Star topologies are easy to manage in most ways but they are far from cheap to set up and use.

3. Ring Network Topology



In networks with ring topology, computers are connected to each other in a circular format. Every device in the network will have two neighbors and no more or no less. Ring topologies were commonly used in the past but you would be hard-pressed to find an enterprise still using them today.

The first node is connected to the last node to link the loop together. As a consequence of being laid out in this format packets need to travel through all network nodes on the way to their destination.

Within this topology, one node is chosen to configure the network and monitor other devices. Ring topologies are half-duplex but can also be made full-duplex. To make ring topologies full-duplex you would need to have two connections between network nodes to form a Dual Ring Topology.

Advantages

With ring topologies, the risk of packet collisions is very low due to the use of token-based protocols, which only allow one station to transmit data at a given time. This is compounded by the fact that data can move through network nodes at high speeds which can be expanded on when more nodes are added.

Disadvantages

One of the reasons why ring topologies were replaced is because they are very vulnerable to failure. The failure of one node can take the entire network out of operation. This means that ring topology networks need to be constantly managed to ensure that all network nodes are in good health. However, even if the nodes were in good health your network could still be knocked offline by a transmission line failure!

Ring topologies also raised scalability concerns. For instance, bandwidth is shared by all devices within the network. In addition, the more devices that are added to a network the more communication delay the network experiences. This means that the number of devices added to a network topology needed to be monitored carefully to make sure that the network resources weren’t stretched beyond their limit.

Making changes to a ring topology was also complicated because you need to shut down the network to make changes to existing nodes or add new nodes. This is far from ideal as you’ll need to factor in downtime every time you want to make a change to the topological structure!

4. Mesh Network



A mesh topology is a point-to-point connection where nodes are interconnected. In this form of topology, data is transmitted via two methods: routing and flooding. Routing is where nodes use routing logic to work out the shortest distance to the packet’s destination. In contrast, flooding is where data is sent to all nodes within the network. Flooding doesn’t require any form of routing logic to work. There are two forms of mesh topology: partial mesh topology and full mesh topology. With partial mesh topology, most nodes are interconnected but there are a few which are only connected to two or three other nodes. A full mesh topology is where every node is interconnected.

Advantages

Mesh topologies are used first and foremost because they are reliable. The interconnectivity of nodes makes them extremely resistant to failures. There is no single machine failure that could bring down the entire network. The absence of a single point of failure is one of the reasons why this is a popular topology choice. This setup is also secure from being compromised.

Disadvantages

However, mesh topologies are far from perfect. They require an immense amount of configuration once they are deployed. The topological layout is more complex than many other topologies and this is reflected by how long it takes to set up. You’ll need to accommodate a whole host of new wiring which can add up to be quite expensive.

5. Flat Networks

Flat networks have become common for small businesses (and ironically enough certain development shops). They’re called “flat networks” because they’re like a flat topology map. There is no high or low, nothing is harder or easier to access from any point in the network. Everything can easily see and talk to everything else.

This is common with most home setups, and a depressing number of small businesses. Traffic goes from the internet, to a modem, then passes through the firewall which is the only “gate” protecting our network. Inside we hit a router and whatever switches or other networking hardware connects everything. There’s probably a wireless network which both guests and employees connect to. Everything can access everything else.

At this point we are relying on nothing internal being trustworthy and our network never being breached. In the days of BYOD and more and more internet connected devices, we are essentially placing our trust in both never being invaded and never being betrayed. Flat networks work in certain scenarios, but not in security.

6. Segmented Networks

Most newer consumer grade routers come with the option for a guest network. The guest network which blocks the one WiFi channel from the rest of the network is the first step in setting up a segmented network. A segmented, or routed network is a network with a nontrivial topology which restricts connections between different nodes on the network.

Despite this being a near trivial example which is available in pretty much any mid-grade consumer router from the past 5 years, this creates a massive improvement in security, but adds a caveat. If you connect to the wrong access point, you can’t communicate with the internal network at all (and this happens to users a lot), but neither can a compromised machine or a malicious actor. You have segmented the network and traffic is routed so that it cannot communicate with something it shouldn’t be able to.

7. Relation Between Network Topology and Security

Network topology impacts security as well as security response. The more segmented the network, the harder it is to breach internally and the harder it is for a breach to spread. A hard hull on a ship is great, but you want rooms which seal inside in case of a breach. Too small of a room or too many rooms and your ship is impractical for cargo or even travel.

You can’t just block every device from every other device in a business (or even most home environments). Devices need to communicate. That’s the beauty of routing though, you can route traffic from certain sources to other sources. You can control what a server exposes to a different part of the network via NAT or other techniques.

The topology can impact specific security ingresses as well as how a response situation happens. You may fail to stop a machine from getting new generation malware, but you can limit its ability to spread and give yourself time to notice. Modern security isn’t about 100% prevention, it’s about the damage control and recovery. The dream of perfect security has long since sailed.

8. Mitigation Techniques

Basic routing and segmentation can obviously slow down many attacks and make others impractical, but newer generation security includes things like internal QoS style directional throttling, internal port blocking, and jump boxes. Sometimes you want a firewall on an internal part of the network. Other times, you want all your Internet of Things or other embedded devices separated for privacy and security.

Some companies treat each site like they’re just some other organization with limited access. Some do this internally between departments, or even teams. It requires heavily investing in network equipment to be practical, but when the zero-day ransomware of the month makes its rounds, the places with the seemingly paranoid security don’t call. They trade convenience for security, and if they get hit, it’s usually a machine or two at most because the infection is localized and quarantined quickly. Since they’re willing to throw money at security, they’re usually also willing to throw money at backups, so the whole ordeal is just an inconvenience at most.
