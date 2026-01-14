### Group 3 ( Section 23412C3) 2023Batch - 5th Semester
#### Name1: SURAJIT SAHOO                    
#### Name2: SATYAJIT SETHY                     
#### Name3: E. SAILAJA                              
#### Name4: TRIBHUWAN SINGH

# 📁 Centralised File Sharing System with DHCP & FTP Server

## 📌 Project Overview
This project demonstrates the design and implementation of a **centralised file sharing system** for a small office environment using **Cisco Packet Tracer**.  
The network is divided into **three departments (HR, IT, Finance)**, each operating on **separate IP subnets** to ensure logical isolation while allowing controlled inter-department communication.

A **centralised DHCP server** automates IP address allocation for all clients, and a **centralised FTP server** enables secure file sharing across departments using authentication.

---

## 🎯 Objectives
- Design a structured departmental network using subnetting  
- Implement centralised DHCP for dynamic IP allocation  
- Enable secure file sharing using an FTP server  
- Allow inter-department communication via static routing  
- Simulate and validate the network using Cisco Packet Tracer  

---

## 🏗️ Network Architecture

### Departments
- HR Department  
- IT Department  
- Finance Department  

Each department:
- Operates on a separate /24 subnet  
- Is connected to the router through an access switch  
- Contains client PCs receiving IP addresses dynamically  

### Core Components
- 1 Router  
- 3 Switches  
- 6 Client PCs  
- 1 Central Server (DHCP + FTP)  

---

## 🌐 IP Addressing Scheme

| Department | Network Address | Subnet Mask | Gateway |
|-----------|----------------|------------|--------|
| HR | 192.168.10.0 | 255.255.255.0 | 192.168.10.1 |
| IT | 192.168.20.0 | 255.255.255.0 | 192.168.20.1 |
| Finance | 192.168.30.0 | 255.255.255.0 | 192.168.30.1 |

- **Server Static IP:** `192.168.20.2`  
- **DHCP Allocation:** Up to 50 hosts per department  

---

## ⚙️ Technologies & Tools Used
- Cisco Packet Tracer  
- DHCP (Dynamic Host Configuration Protocol)  
- FTP (File Transfer Protocol)  
- Static Routing  
- Subnetting  

---

## 🔧 Configuration Details

### 1️⃣ Router Configuration
- Static IP assigned to each interface  
- Each interface is mapped to a department subnet  
- Enables inter-subnet routing  

Example:
interface g0/0
ip address 192.168.10.1 255.255.255.0
no shutdown

## DHCP Server Configuration
Centralised DHCP server hosted in IT department
Separate DHCP pools for HR, IT, and Finance
DHCP relay configured using ip helper-address

Advantages:
- Eliminates manual IP configuration
- Prevents IP conflicts
- Simplifies network management

## FTP Server Configuration

- FTP service enabled on the central server
- Authentication-based access control
- Department-wise user accounts created

Username	Password	Permission
- cisco	cisco	Read/Write
- hruser	hr123	Read/Write
- ituser	it123	Read/Write
- finuser	fin123	Read/Write

FTP operations tested for:
- File upload
- File download
- Cross-department access

### ✅ Results & Verification
✔ DHCP Verification
- All client PCs received IP addresses dynamically
- Correct subnet, gateway, and DNS assigned
✔ Inter-Department Connectivity
Verified using ping command
-Successful ICMP responses between all subnets
✔ FTP File Transfer
-File uploaded from HR department
-File downloaded from Finance department
-Confirms successful centralised file sharing
-ip address 192.168.10.1 255.255.255.0
-no shutdown
