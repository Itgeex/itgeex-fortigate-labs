# Lab 13 – Full Enterprise Network Design (Capstone Project)

## 📌 Overview
This capstone lab represents a **full end-to-end enterprise network design**
using FortiGate as the core security and routing platform.

The lab combines all previous concepts into a **realistic production-grade architecture**
covering security, networking, availability, monitoring, and operations.

---

## 🎯 Objectives
- Design an enterprise-ready network architecture
- Implement security best practices end-to-end
- Integrate HA, VPN, SD-WAN, NGFW, ZTNA, and Monitoring
- Apply dynamic routing and segmentation
- Demonstrate operational readiness

---

## 🧱 Enterprise Scenario

### 🏢 Organization Profile
- 1 × Headquarters
- 2 × Branch Offices
- Remote users
- On-prem services + Internet access

### 👥 Users
- IT Admins
- Office Users
- Remote Employees
- External Vendors

---

## 🧠 Architecture Components

### 🔐 Security
- FortiGate NGFW
- Security Profiles (IPS / AV / Web Filter)
- SSL VPN & ZTNA
- Zero Trust principles

### 🖧 Network
- SD-WAN (Dual ISP per site)
- IPsec Site-to-Site VPN
- OSPF (Internal routing)
- BGP (Inter-site routing)

### 🛠 Operations
- HA Active/Passive
- Centralized Logging
- Monitoring & Alerting
- Incident Response workflows

---

## 🗺 Network Topology

- HQ FortiGate HA Cluster
- Branch FortiGates
- IPsec VPN tunnels
- SD-WAN across ISPs
- Segmented VLANs:
  - Users
  - Servers
  - Management
  - Guest

📌 (Topology diagram recommended)

---

## ⚙️ Implementation Phases

### Phase 1 – Core Network & HA
- Deploy FortiGate HA at HQ
- Configure VLAN segmentation
- Enable baseline security

---

### Phase 2 – WAN, VPN & SD-WAN
- Configure Dual WAN links
- Enable SD-WAN
- Establish Site-to-Site VPNs
- Apply SLA-based routing

---

### Phase 3 – Routing
- Deploy OSPF internally
- Use BGP for inter-site routing
- Implement route filtering

---

### Phase 4 – Security Enforcement
- Apply NGFW profiles
- Harden firewall policies
- Enable SSL inspection

---

### Phase 5 – Remote Access & ZTNA
- Configure SSL VPN
- Implement ZTNA for applications
- Enforce MFA and device posture

---

### Phase 6 – Monitoring & Incident Response
- Centralize logs
- Configure alerts
- Define IR playbooks

---

## 🧪 Validation & Testing

### 🔬 Test Scenarios
- WAN failure
- HA failover
- VPN outage
- Unauthorized access attempt
- Malware simulation

Expected Results:
- Zero downtime (where applicable)
- Automatic failover
- Secure access enforced
- Incidents detected & logged

---

## 📄 Documentation Deliverables

- Network diagrams
- IP addressing plan
- Security policy matrix
- Routing design
- Monitoring dashboards
- Incident response playbooks

---

## 🔐 Security & Compliance
- Least privilege
- Zero Trust access
- Logging & audit readiness
- Change management documentation

---

## 📈 Outcome
After completing this capstone:
- Enterprise network is fully designed
- Architecture is scalable & secure
- Operations are mature
- Design is production-ready

---

## 🏁 Final Result
This lab demonstrates:
- Senior-level engineering
- Security-first architecture
- End-to-end responsibility
- Real-world readiness

---

## 🎉 Congratulations
You have completed the **ITGEEX Enterprise FortiGate Lab Series** 🎯
