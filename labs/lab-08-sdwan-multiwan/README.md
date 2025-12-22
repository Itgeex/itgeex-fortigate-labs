# Lab 08 – FortiGate SD-WAN & Multi-WAN

## 📌 Overview
This lab demonstrates how to design, configure, and validate
**SD-WAN and Multi-WAN** on FortiGate to achieve
high availability, load balancing, and intelligent traffic steering.

The goal is to improve **performance, resiliency, and application experience**.

---

## 🎯 Objectives
- Configure multiple WAN links
- Enable SD-WAN
- Define health checks (SLA)
- Apply intelligent traffic steering
- Implement failover and load balancing
- Monitor SD-WAN performance

---

## 🧱 Lab Environment
- FortiGate Firewall
- WAN1 (ISP-A)
- WAN2 (ISP-B)
- LAN network
- Internet access

---

## 🧠 SD-WAN Design Principles
- Application-aware routing
- SLA-based decision making
- Automatic failover
- Cost-effective bandwidth usage

📌 SD-WAN replaces traditional static WAN failover.

---

## ⚙️ Step 1 – WAN Interface Preparation

- Configure WAN1 and WAN2
- Assign IP addresses
- Verify internet connectivity
- Disable management access on WAN interfaces

---

## ⚙️ Step 2 – Enable SD-WAN

Navigate to:
`Network → SD-WAN`

- Enable SD-WAN
- Add WAN1 and WAN2 as SD-WAN members
- Assign interface priorities (optional)

---

## ⚙️ Step 3 – Health Check (SLA) Configuration

### 📡 Define Performance SLAs
Create health checks:
- DNS probe (8.8.8.8)
- HTTP probe
- Latency / Jitter / Packet Loss thresholds

Example:
- Latency < 150 ms
- Packet Loss < 5%

📌 SLA defines link quality, not just availability.

---

## ⚙️ Step 4 – SD-WAN Rules (Traffic Steering)

Navigate to:
`Network → SD-WAN Rules`

Create rules based on:
- Application
- Source/Destination
- SLA compliance

Examples:
- Business apps → Best quality link
- Internet browsing → Load balance
- VoIP → Lowest latency

---

## ⚙️ Step 5 – Firewall Policy Integration

- Create LAN → SD-WAN policy
- Enable NAT
- Attach Security Profiles (IPS / AV / Web Filter)

📌 SD-WAN policies replace traditional WAN policies.

---

## ⚙️ Step 6 – Load Balancing & Failover

### 🔁 Load Balancing
- Spillover
- Session-based
- Volume-based

### 🔄 Failover
- Automatic based on SLA violation
- No manual intervention required

---

## ⚙️ Step 7 – Monitoring & Analytics

Navigate to:
`Network → SD-WAN Monitor`

Monitor:
- Link status
- SLA compliance
- Traffic distribution
- Application usage

---

## 🧪 Step 8 – Validation & Testing

### 🔬 Test Scenarios
- Disconnect WAN1 → Verify failover
- Simulate latency increase
- Generate VoIP & HTTP traffic

Expected Results:
- Traffic rerouted automatically
- SLA-based decisions applied
- No session drops (where possible)

---

## 🔍 Troubleshooting

| Issue | Cause |
|-----|------|
| No failover | SLA too loose |
| Traffic on wrong WAN | Rule order |
| Flapping | Aggressive SLA |
| No internet | Policy misconfiguration |

Useful CLI:
diagnose sys sdwan health-check
diagnose sys sdwan service

---

## 🔐 Best Practices
- Use multiple SLA probes
- Separate business vs non-critical traffic
- Combine SD-WAN with security profiles
- Monitor trends, not just failures

---

## 📄 Outcome
After completing this lab:
- WAN links are intelligent and resilient
- Application experience is optimized
- Failover is automatic and transparent
- Network is enterprise-ready

---

## 📌 Next Lab
➡ **Lab 09 – SSL VPN & User-Based Access Control**
