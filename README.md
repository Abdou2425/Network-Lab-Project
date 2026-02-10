# Network Lab Project
![Cisco](https://img.shields.io/badge/Cisco-PacketTracer-blue?style=for-the-badge)
![Networking](https://img.shields.io/badge/Networking-Lab-green?style=for-the-badge)

## Overview
This project is a **network lab designed and implemented using Cisco Packet Tracer**.  
It demonstrates advanced networking concepts including **routing protocols, DHCP, DNS, FTP, Web services, and extended access control lists (ACLs)**.

The network is divided into **four major sub-networks**, each with its own router and internal topology, simulating a real-world enterprise network environment.

Developed as part of an **academic network laboratory project for the Advanced Networks module**.

---
## 🎯 Network Architecture

- The network consists of **4 large sub-networks (Subnetwork 0 → Subnetwork 3)**.
- Each sub-network has:
  - Its **own routers**
  - An **internal local network**
- Routing protocols are implemented to ensure full connectivity and control.
### 🌐 Routing Protocols
- **OSPF routing** is used across all sub-networks:
  - Subnetwork 0 → **OSPF Area 0**
  - Subnetwork 1 → **OSPF Area 1**
  - Subnetwork 2 → **OSPF Area 2**
  - Subnetwork 3 → **OSPF Area 3**
- **EIGRP** is used **only in Subnetwork 1**
- **Route redistribution** is configured on **Router 0** to link **EIGRP with OSPF**

---
## 🖧 Sub-Network Services
### 🖧 Subnetwork 0
- contains:
  - **3 routers**
  -  Acts as the **core network** of the topology, connects all other subnetworks using OSPF area 0
### 🖥️ Subnetwork 1
- use EIGRP for all 3 routers(routeur 0,1,2) and all interfaces
- use OSPF area1 only in int se6/0 in router 0 
- router 0 links between OPSF and EIGRP 
- Contains:
  - **Web Server**
  - **FTP Server**
  - **3 Routers and 1PC**
- Web service is accessible via HTTP / HTTPS.
- Web service is accessible via DNS using:
  - **www.Abed.com**
- FTP server is configured with:
  - **username: abdou**
  - **password: abed**
- FtP testing:
  ```bash
    ftp <ftp-server-ip>
  ```
### 🌐 Subnetwork 2
- use OSPF area 2
- Contains:
- **1 router and 1pc**
- **DNS Server**
- DNS server is configured to resolve:
  -  www.abed.com → Web Server IP (Subnetwork 1)
### 📡 Subnetwork 3
- use OPSF area 3
- Contains:
- **1 router, 1 switch and 4 pc**
- **DHCP Server**
- DHCP dynamically provides:
- IP address
- Subnet mask
- Default gateway
- DNS server IP

---
## 🔁 IP Addressing & Routing

- **Static IP addressing** is used in all sub-networks
- **Exception**:
- Subnetwork 3 uses **DHCP** for client IP configuration

---
## 🔐 Security – Extended Access Control Lists (ACL)

### 🚫 ACL Rule – Subnetwork 2
- Router: **Router 6**
- Interface: **FastEthernet 0/0**
- Rule:
- **PC1 is denied communication with the Web Server**

### 🚫 ACL Rule – Subnetwork 3
- Router: **Router 7**
- Interface: **FastEthernet 0/0**
- Rule:
- **PC05 is denied access to the Web Server on ports greater than 1000**
#### 🔍 Testing:
- From **PC01**, try fom command prompt :
 **ping <ip-server-web,>**

- From **PC05**, try accessing:
  **http://<web-server-ip,>:1000+**

## 🛠️ Tools & Technologies

- **Cisco Packet Tracer** – Network design and simulation
- **Routing Protocols** – OSPF, EIGRP
- **Network Services** – DNS, DHCP, FTP, HTTP
- **Security** – Extended Access Control Lists (ACLs)
## 👤 Author

- **Abed Abderrahmane**
## 📜 License

This project was created for **educational purposes** as part of a **network laboratory academic project**.

