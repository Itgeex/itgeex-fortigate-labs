# Lab 02 – Firewall Policies & NAT (Deep Dive)

## 📌 Overview
This lab provides an in-depth, practical understanding of FortiGate
firewall policies and NAT behavior.

The focus is on **policy design, order of processing, security best practices,
and real-world troubleshooting**, not just allowing traffic.

---

## 🎯 Objectives
- Understand FortiGate policy processing logic
- Create secure firewall policies
- Configure Source NAT correctly
- Apply logging and policy best practices
- Troubleshoot common policy-related issues

---

## 🧱 Lab Environment

### 🔧 Devices
- FortiGate Firewall (Configured from Lab 01)
- Internal Client (LAN)
- Internet / Upstream Network

### 🌐 Network Topology
![Lab 02 – Firewall Policies & NAT Topology](lab02-topology.png)

---

## 🧠 FortiGate Policy Processing (Concept)
FortiGate processes firewall policies:
1. **Top to Bottom**
2. **First Match Wins**
3. Implicit deny at the bottom

📌 A poorly ordered policy can break connectivity or reduce security.

---

## ⚙️ Step 1 – Clean Up Existing Policies
Before starting:
- Remove any temporary or overly permissive rules from Lab 01
- Ensure policy table is clean and readable

---

## ⚙️ Step 2 – Create Address Objects

### 📍 Internal Network
- Name: `LAN_SUBNET`
- Type: Subnet
- Address: `192.168.10.0/24`

### 🌍 Internet Access
- Use built-in `all` object (for lab purposes only)

📌 Best Practice:
- Always use **Address Objects**, never raw IPs in policies

---

## ⚙️ Step 3 – Create a Basic LAN → WAN Policy

### 🔐 Policy Configuration
- Name: `LAN_to_Internet`
- Incoming Interface: `LAN`
- Outgoing Interface: `WAN`
- Source: `LAN_SUBNET`
- Destination: `all`
- Service: `ALL` (will be restricted later)
- Action: `ACCEPT`
- NAT: `ENABLE`
- Log Allowed Traffic: `ALL SESSIONS`

📌 This policy enables controlled internet access from LAN.

---

## ⚙️ Step 4 – Understand NAT Behavior

### 🧠 Source NAT (SNAT)
- Translates private IPs to WAN IP
- Required for internet access
- Typically enabled per policy

### 🔍 Verification
- Check active sessions
- Verify translated source IP
- Review Forward Traffic logs

---

## ⚙️ Step 5 – Restrict Services (Security Best Practice)

Instead of `ALL`, create a service group:
- HTTP
- HTTPS
- DNS
- NTP

### ✳️ Update Policy
- Replace `ALL` service with the new service group

📌 Principle of Least Privilege applies to firewall services.

---

## ⚙️ Step 6 – Policy Logging & Visibility

### 🔍 Logging Settings
- Enable:
  - Allowed traffic (All Sessions)
- Disable unnecessary logging on deny rules if noisy

### 📊 Benefits
- Troubleshooting
- Auditing
- Incident analysis

---

## ⚙️ Step 7 – Policy Order Optimization

Ensure order:
1. Specific rules (e.g., management access)
2. User or service-specific policies
3. General internet access
4. Explicit deny (optional, documented)

📌 Never rely only on implicit deny in production.

---

## 🧪 Step 8 – Validation & Testing
From internal client:
- Test web access
- Test DNS resolution
- Verify NAT functionality
- Review firewall logs

Expected Result:
- Traffic allowed only by defined services
- Logs visible and readable

---

## 🔍 Troubleshooting Common Issues

| Issue | Possible Cause |
|-----|---------------|
| No internet | NAT disabled |
| Policy not hit | Wrong policy order |
| DNS not working | DNS service missing |
| Traffic denied | Wrong interface direction |

Useful CLI commands:
diagnose debug flow
diagnose sys session list

---

## 🔐 Security Best Practices
- Avoid `ANY → ANY → ALL`
- Use address and service objects
- Enable logging on critical policies
- Document policy purpose
- Review and clean unused policies regularly

---

## 📄 Outcome
At the end of this lab:
- Firewall policies are structured and readable
- NAT is correctly applied
- Traffic is controlled, logged, and secure
- FortiGate is ready for advanced policies and VPN scenarios

---

## 📌 Next Lab
➡ **Lab 03 – Site-to-Site IPsec VPN (FortiGate ↔ FortiGate)**
