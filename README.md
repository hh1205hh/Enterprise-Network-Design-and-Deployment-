# Enterprise Network Design and Deployment: Mentora Nexus

This repository contains a comprehensive enterprise network project for a fictional company, "Mentora Nexus," built entirely within **Cisco Packet Tracer**. [cite\_start]The project, authored by Haim Levhar[cite: 655], details the design, implementation, and configuration of a complex, three-branch network designed for security, redundancy, and scalability.

[cite\_start]The full documentation, `Project_Report_Final.docx`[cite: 654], contains all topology diagrams, IP addressing schemes, and detailed explanations for every configuration.

## Network Overview

[cite\_start]The "Mentora Nexus" network consists of a main branch (Codeport) and two additional branches (TechVista and NeoCyberia), all interconnected via an ISP framework[cite: 763, 795].

  * [cite\_start]**Codeport (Main Branch):** The central hub, hosting the company's primary web, mail, and DNS servers[cite: 802, 848].
  * [cite\_start]**TechVista Branch:** A standard branch office[cite: 768].
  * [cite\_start]**NeoCyberia Branch:** A second standard branch office[cite: 772].

## Key Features & Technologies Implemented

This project serves as a practical demonstration of a wide range of networking concepts, from foundational services to advanced routing and security.

### Routing & Redundancy

  * [cite\_start]**OSPF (Open Shortest Path First):** Implemented for all internal routing within the branches[cite: 724, 1079].
  * [cite\_start]**BGP (Border Gateway Protocol):** Used for external routing between the three branches and the ISP[cite: 726, 1102].
  * [cite\_start]**HSRP (Hot Standby Router Protocol):** Configured to provide first-hop redundancy and gateway failover for end-user VLANs[cite: 728, 1119].
  * [cite\_start]**EtherChannel:** Deployed between distribution and access layer switches for link aggregation and high availability[cite: 731, 1166].

### Security

  * [cite\_start]**IPsec VPN (Site-to-Site):** Secure tunnels are built between all three branches to protect data in transit over the public ISP network[cite: 729, 897].
  * [cite\_start]**GRE Tunnels:** Used in conjunction with IPsec to route dynamic routing protocols (OSPF) securely between sites[cite: 730, 1151].
  * [cite\_start]**AAA (Authentication, Authorization, & Accounting):** TACACS+ is configured for centralized and secure device management and login[cite: 721, 1017].
  * [cite\_start]**Access Control Lists (ACLs):** Deployed for traffic filtering and securing VTY lines[cite: 765, 1300].
  * [cite\_start]**L2 Security:** Includes DHCP Snooping [cite: 1278][cite\_start], ARP Inspection [cite: 1277][cite\_start], and PortFast/BPDU Guard[cite: 1236, 1243].

### Core Network Services

A full suite of enterprise services is configured on dedicated servers:

  * [cite\_start]**DNS:** Provides name resolution for internal services (e.g., `mentoranexus.com`) and external domains[cite: 714, 917].
  * [cite\_start]**DHCP:** Dynamically assigns IP addresses to clients in each VLAN[cite: 722, 1050].
  * [cite\_start]**HTTP/HTTPS:** A central web server hosts the company website, `mentoranexus.com`[cite: 715, 924].
  * [cite\_start]**Mail (SMTP & POP3):** A complete mail server (`mail.mentoranexus.com`) is set up to allow email exchange between employees[cite: 720, 998, 1000].
  * [cite\_start]**FTP / TFTP:** Servers for file storage and transferring network device configurations[cite: 716, 717, 933, 949].
  * [cite\_start]**NTP:** Provides accurate time synchronization across all network devices[cite: 719, 981, 989].
  * [cite\_start]**Syslog:** A central server for aggregating and storing logs from routers and switches[cite: 718, 966].

### Layer 2 Switching

  * [cite\_start]**VLANs:** The network is segmented into separate VLANs for each department (e.g., Management, IT, Finance) to improve security and manage broadcast traffic[cite: 817, 820, 825].
  * [cite\_start]**VTP (VLAN Trunking Protocol):** Used to manage and synchronize VLAN information across switches in the TechVista and NeoCyberia branches[cite: 733, 860, 862, 1203].
  * [cite\_start]**RSTP (Rapid Spanning Tree Protocol):** The default IEEE 802.1w protocol is active to ensure a loop-free Layer 2 topology[cite: 734].

## How to Use

1.  **Software:** You must have **Cisco Packet Tracer** (version 8.2 or later recommended) installed to open the project files.
2.  **Project Files:** The primary simulation files are located in the `Network_Simulation/Project_Files/` directory.
3.  [cite\_start]**Documentation:** The complete **`Project_Report_Final.docx`** [cite: 654] is the main guide. [cite\_start]It contains all logical/physical topologies, IP allocation tables, device credentials[cite: 828], and detailed explanations for all configurations.
4.  **Config Snippets:** The `Devices_Configurations/` directory contains `.docx` files with configuration excerpts for specific technologies (BGP, IPsec, etc.) for quick reference.

## Repository Structure

```
├── Devices_Configurations/   # Standalone config files for BGP, GRE, IPsec, etc.
├── Net_concepts/             # Q&A doc for networking concepts
├── Network_Requirements/     # Initial requirements and organizational charts
├── Network_Simulation/
│   ├── Images/             # Topology diagrams, maps, and logos
│   └── Project_Files/        # Cisco Packet Tracer (.pkt) files
├── Project_Report_Final.docx # The complete, detailed project report
├── Project_Report_Final.pdf  # PDF version of the report
└── README.md                 # This file
```
