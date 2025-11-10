# Enterprise Network Design and Deployment: Mentora Nexus

This repository contains a comprehensive enterprise network project for a fictional company, "Mentora Nexus," built entirely within **Cisco Packet Tracer**. The project, authored by Haim Levhar, details the design, implementation, and configuration of a complex, three-branch network designed for security, redundancy, and scalability.

The full documentation, `Project_Report_Final.docx`, contains all topology diagrams, IP addressing schemes, and detailed explanations for every configuration.

## Network Overview

The "Mentora Nexus" network consists of a main branch (Codeport) and two additional branches (TechVista and NeoCyberia), all interconnected via an ISP framework.

  * **Codeport (Main Branch):** The central hub, hosting the company's primary web, mail, and DNS servers.
  * **TechVista Branch:** A standard branch office.
  * **NeoCyberia Branch:** A second standard branch office.

## Key Features & Technologies Implemented

This project serves as a practical demonstration of a wide range of networking concepts, from foundational services to advanced routing and security.

### Routing & Redundancy

  * **OSPF (Open Shortest Path First):** Implemented for all internal routing within the branches.
  * **BGP (Border Gateway Protocol):** Used for external routing between the three branches and the ISP.
  * **HSRP (Hot Standby Router Protocol):** Configured to provide first-hop redundancy and gateway failover for end-user VLANs.
  * **EtherChannel:** Deployed between distribution and access layer switches for link aggregation and high availability.

### Security

  * **IPsec VPN (Site-to-Site):** Secure tunnels are built between all three branches to protect data in transit over the public ISP network.
  * **GRE Tunnels:** Used in conjunction with IPsec to route dynamic routing protocols (OSPF) securely between sites.
  * **AAA (Authentication, Authorization, & Accounting):** TACACS+ is configured for centralized and secure device management and login.
  * **Access Control Lists (ACLs):** Deployed for traffic filtering and securing VTY lines.
  * **L2 Security:** Includes DHCP Snooping, ARP Inspection, and PortFast/BPDU Guard.

### Core Network Services

A full suite of enterprise services is configured on dedicated servers:

  * **DNS:** Provides name resolution for internal services (e.g., `mentoranexus.com`) and external domains.
  * **DHCP:** Dynamically assigns IP addresses to clients in each VLAN.
  * **HTTP/HTTPS:** A central web server hosts the company website, `mentoranexus.com`.
  * **Mail (SMTP & POP3):** A complete mail server (`mail.mentoranexus.com`) is set up to allow email exchange between employees.
  * **FTP / TFTP:** Servers for file storage and transferring network device configurations.
  * **NTP:** Provides accurate time synchronization across all network devices.
  * **Syslog:** A central server for aggregating and storing logs from routers and switches.

### Layer 2 Switching

  * **VLANs:** The network is segmented into separate VLANs for each department (e.g., Management, IT, Finance) to improve security and manage broadcast traffic.
  * **VTP (VLAN Trunking Protocol):** Used to manage and synchronize VLAN information across switches in the TechVista and NeoCyberia branches.
  * **RSTP (Rapid Spanning Tree Protocol):** The default IEEE 802.1w protocol is active to ensure a loop-free Layer 2 topology.

## How to Use

1.  **Software:** You must have **Cisco Packet Tracer** (version 8.2 or later recommended) installed to open the project files.
2.  **Project Files:** The primary simulation files are located in the `Network_Simulation/Project_Files/` directory.
3.  **Documentation:** The complete **`Project_Report_Final.docx`** is the main guide. It contains all logical/physical topologies, IP allocation tables, device credentials, and detailed explanations for all configurations.
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
