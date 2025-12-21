# Lab 06 – FortiGate Hardening & Security Baseline

## 📌 Overview
This lab focuses on **hardening FortiGate firewalls** to meet
enterprise security and operational best practices.

The goal is to reduce the attack surface, protect management access,
and prepare the firewall for production environments and audits.

---

## 🎯 Objectives
- Secure management access
- Apply strong authentication and authorization
- Harden network and service exposure
- Improve logging, monitoring, and visibility
- Align FortiGate configuration with security best practices

---

## 🧱 Lab Environment
- FortiGate Firewall (Standalone or HA Cluster)
- Administrative access to GUI & CLI

---

## 🧠 Hardening Principles
- Principle of Least Privilege
- Defense in Depth
- Secure by Default
- Audit & Traceability

---

## ⚙️ Step 1 – Admin & Management Hardening

### 🔐 Admin Accounts
- Disable default `admin` account (or restrict heavily)
- Create named admin users
- Use **role-based admin profiles**
- Enforce strong password policy
- Enable password expiration

### 🔒 Management Access
- Disable HTTP (use HTTPS only)
- Restrict management access by:
  - Trusted IPs
  - Dedicated management interface
- Disable unused management services (SSH, Telnet)

---

## ⚙️ Step 2 – Authentication & Authorization

- Integrate with:
  - LDAP / Active Directory (if available)
- Enable two-factor authentication (2FA) for admins
- Apply least-privilege admin roles
- Log all admin actions

📌 Never share admin accounts.

---

## ⚙️ Step 3 – Interface & Network Hardening

- Disable unused interfaces
- Disable administrative access on WAN
- Allow only required services per interface
- Use dedicated management interface where possible
- Enable anti-spoofing

---

## ⚙️ Step 4 – Policy & NAT Hardening

- Remove `ANY → ANY → ALL` policies
- Restrict services and destinations
- Use address and service objects
- Enable logging on security-critical policies
- Review and clean unused policies

---

## ⚙️ Step 5 – VPN Hardening

- Use IKEv2 for IPsec VPNs
- Enable PFS
- Use strong encryption:
  - AES256
  - SHA256+
- Rotate PSKs regularly
- Restrict VPN traffic with policies

---

## ⚙️ Step 6 – System & OS Hardening

- Disable unused features and services
- Enable automatic configuration backups
- Restrict local-in policies
- Harden admin GUI settings
- Configure session timeouts

---

## ⚙️ Step 7 – Logging, Monitoring & Alerts

- Enable:
  - Admin login/logout logs
  - Configuration change logs
  - VPN events
  - Traffic logs
- Forward logs to:
  - FortiAnalyzer / Syslog
- Configure alerts for:
  - HA failover
  - VPN down
  - Admin login failures

---

## ⚙️ Step 8 – Firmware & Maintenance

- Keep firmware updated (tested versions only)
- Follow upgrade path recommendations
- Schedule maintenance windows
- Backup configuration before and after upgrades

---

## 🧪 Validation Checklist

✔ Admin access restricted  
✔ Unused services disabled  
✔ Policies reviewed and documented  
✔ VPN encryption verified  
✔ Logs visible and forwarded  

---

## 🔍 Common Hardening Mistakes
- Leaving default admin enabled
- Managing firewall from WAN
- Over-permissive firewall rules
- No logging or log retention
- No regular review process

---

## 📄 Outcome
After completing this lab:
- FortiGate is hardened and production-ready
- Management plane is secured
- Configuration is auditable
- Attack surface is minimized

---

## 📌 Next Lab
➡ **Lab 07 – Monitoring & Logging (PRTG / FortiAnalyzer / Syslog)**
