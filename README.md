# 🧰 IT Support Virtual Lab – Windows Server & DHCP Configuration

## 📋 Project Overview
This project demonstrates the setup of a **virtual IT infrastructure** using **Oracle VirtualBox**, including a Windows Server 2022 domain controller and a Windows 10 client machine.  
It replicates a small business network environment where the server manages DHCP, DNS, and domain services for client machines.

---

## 🖥️ Environment
- **Host OS:** Windows 11  
- **Virtualization Tool:** Oracle VirtualBox  
- **Virtual Machines:**
  - `Server-DC` → Windows Server 2022 Standard Evaluation  
  - `Client-Win10` → Windows 10 Enterprise  
- **Network Configuration:**
  - Adapter 1: *Internal Network* (`labnet`)  
  - Adapter 2: *NAT* (for internet access)

---

## ⚙️ Configuration Summary

### 🧩 Windows Server 2022 – Domain Controller (Server-DC)
**Roles Installed:**
- DHCP Server
- Active Directory Domain Services (AD DS)
- DNS Server (to be configured next)

**Tasks Performed:**
1. Installed Windows Server 2022 Standard Evaluation.
2. Configured two network adapters:
   - Adapter 1 (Internal): 192.168.10.1 — for internal lab communication.
   - Adapter 2 (NAT): for external internet connectivity.
3. Installed and configured DHCP Server:
   - Created a new scope named `lab.local`.
   - IP range: `192.168.10.10 – 192.168.10.100`
   - Subnet Mask: `255.255.255.0`
   - Default Gateway: `192.168.10.1`
   - DNS Server: `192.168.10.1`
4. Authorized and activated the DHCP server.
5. Verified lease distribution and communication with the Windows 10 client.

---

### 💻 Windows 10 Client (Client-Win10)
**Tasks Performed:**
1. Installed Windows 10 Enterprise on VirtualBox.
2. Configured network adapters identical to the server:
   - Adapter 1 (Internal Network): `labnet`
   - Adapter 2 (NAT): for internet access
3. Verified network configuration using:
   ```bash
   ipconfig /release
   ipconfig /renew
# IT-Support-Lab-Windows-Server
