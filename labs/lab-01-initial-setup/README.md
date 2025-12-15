# Lab 01 – FortiGate Initial Setup & Base Configuration

## 📌 Overview
This lab covers the initial deployment and base configuration of a FortiGate firewall.
The goal is to prepare a secure and operational FortiGate device suitable for
enterprise environments.

This lab focuses on **clean design, security-first configuration, and operational readiness**.

---

## 🎯 Objectives
- Perform initial FortiGate setup
- Configure management access securely
- Configure interfaces and basic routing
- Verify connectivity and management access
- Apply baseline security best practices

---

## 🧱 Lab Environment

### 🔧 Devices
- FortiGate Firewall (Physical or VM)
- Management PC / Laptop

### 🌐 Network Topology
'''text
     [ Internet ]
          |
        (WAN)
    [ FortiGate ]
    |           |
  (LAN)      (MGMT)
         |
[ Internal Network ]
'''

---

### 🧩 Assumptions
- FortiGate is freshly installed or factory reset
- WAN interface is connected to upstream router or ISP
- LAN interface connects to internal network

---

## ⚙️ Step 1 – Initial Access & Login
1. Connect a PC to the FortiGate LAN interface
2. Set PC IP address:
IP: 192.168.1.10
Mask: 255.255.255.0
3. Access FortiGate GUI:
Username: admin
Password: (empty)
5. Set a strong administrator password

---

## ⚙️ Step 2 – Change Default Settings (Security Baseline)

### 🔐 Admin Security
- Change admin password to a strong password
- Create a new admin user (optional but recommended)
- Disable HTTP management (use HTTPS only)
- Restrict admin access by trusted IPs if possible

**Best Practice:**
- Do not use default `admin` account for daily operations

---

## ⚙️ Step 3 – Interface Configuration

### 🌐 WAN Interface
- Configure WAN interface with:
- Static IP / DHCP / PPPoE (based on ISP)
- Enable:
- Ping (for troubleshooting)
- Disable unnecessary management access

### 🏠 LAN Interface
- Configure LAN IP address:
192.168.10.1/24
  - Enable:
- HTTPS
- PING
- Configure DHCP Server (optional)

---

## ⚙️ Step 4 – Basic Routing
- Verify default route:
0.0.0.0/0 → ISP Gateway
  - Ensure FortiGate can reach the internet:
- Test using `ping` or `execute ping 8.8.8.8`

---

## ⚙️ Step 5 – DNS & System Settings
- Configure system DNS servers
- Set correct:
- Time zone
- NTP servers
- Enable automatic firmware update checks (manual upgrade recommended)

---

## ⚙️ Step 6 – Basic Firewall Policy

### 🔐 Create First Policy
- Source: LAN
- Destination: WAN
- Service: ALL (temporary for lab)
- Action: ACCEPT
- NAT: ENABLED
- Logging: ENABLED (All Sessions)

📌 This policy is for **initial connectivity testing only**

---

## 🧪 Step 7 – Validation & Testing
- Ping internet from internal client
- Browse a public website
- Verify logs in:
- Log & Report → Forward Traffic

---

## 🔍 Troubleshooting Tips
- Check interface status
- Verify routing table
- Confirm NAT is enabled
- Review firewall logs
- Use CLI tools:
diagnose debug flow
execute ping

---

## 🔐 Security Notes
- Remove temporary wide-open policies after testing
- Restrict management access
- Backup configuration after initial setup
- Document interface IPs and access rules

---

## 📄 Outcome
At the end of this lab, the FortiGate firewall is:
- Securely accessible
- Properly networked
- Ready for advanced configurations (VPN, security profiles, HA)

---

## 📌 Next Lab
➡ **Lab 02 – Firewall Policies & NAT (Deep Dive)**
