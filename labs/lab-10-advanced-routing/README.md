# Lab 10 – FortiGate Advanced Routing (OSPF / BGP)

## 📌 Overview
This lab covers **advanced dynamic routing protocols (OSPF & BGP)**
implemented on FortiGate firewalls.

The goal is to design **scalable, resilient, and enterprise-grade routing**
for complex network environments.

---

## 🎯 Objectives
- Configure OSPF for internal routing
- Configure BGP for external or multi-site routing
- Control routing behavior using metrics and policies
- Verify route propagation and failover
- Troubleshoot dynamic routing issues

---

## 🧱 Lab Environment
- FortiGate Firewall
- Multiple internal networks
- WAN / VPN connections
- Optional: Multiple FortiGates or routers

---

## 🧠 Routing Design Principles
- Dynamic routing over static routes
- Fast convergence
- Controlled route advertisement
- Clear separation of IGP and EGP roles

📌 OSPF = Internal | BGP = External

---

## ⚙️ Part 1 – OSPF Configuration

### 🌀 OSPF Overview
Use OSPF for:
- Internal network routing
- HA environments
- Large-scale LAN/WAN designs

---

### ⚙️ Step 1 – Enable OSPF

Navigate to:
`Network → OSPF`

Configure:
- Router ID
- Areas (Area 0 as backbone)

---

### ⚙️ Step 2 – OSPF Interfaces

Add interfaces:
- Internal interfaces
- VPN tunnels (if required)

Set:
- Network type
- Cost
- Authentication (recommended)

---

### ⚙️ Step 3 – Route Advertisement

Advertise:
- Internal subnets
- Loopback interfaces

Avoid advertising:
- WAN public networks

---

### ⚙️ Step 4 – OSPF Verification

Check:
- Neighbor adjacency
- Routing table
- Convergence time

Useful CLI:
get router info ospf neighbor
get router info routing-table ospf

---

## ⚙️ Part 2 – BGP Configuration

### 🌐 BGP Overview
Use BGP for:
- Multi-site VPN routing
- ISP connectivity
- SD-WAN route control

---

### ⚙️ Step 5 – BGP Setup

Navigate to:
`Network → BGP`

Configure:
- Local AS number
- Router ID
- Neighbor IP & remote AS

---

### ⚙️ Step 6 – Network Advertisement

Advertise:
- Internal networks
- VPN-connected subnets

Control:
- Prefix lists
- Route maps

📌 Never advertise full routing table unless required.

---

### ⚙️ Step 7 – Path Control & Policies

- Local Preference
- MED
- AS-PATH prepend
- Route filtering

---

### ⚙️ Step 8 – BGP Verification

Check:
- Neighbor state
- Received/advertised routes
- Best path selection

Useful CLI:
get router info bgp summary
get router info bgp neighbors

---

## 🔁 Routing with VPN & SD-WAN

- Use OSPF over IPsec tunnels
- Use BGP for multi-site full-mesh
- Combine with SD-WAN SLA

📌 Dynamic routing removes manual tunnel route management.

---

## 🧪 Validation & Testing

### 🔬 Test Scenarios
- Interface failure
- Tunnel down
- Route change propagation

Expected Results:
- Fast reconvergence
- No traffic blackhole
- Correct route selection

---

## 🔍 Troubleshooting

| Issue | Cause |
|-----|------|
| No OSPF neighbor | Area mismatch |
| Routes missing | Network not advertised |
| BGP stuck in Active | AS or IP mismatch |
| Route loops | Missing filters |

---

## 🔐 Best Practices
- Authenticate routing protocols
- Use route filtering
- Monitor routing changes
- Document AS numbers & areas

---

## 📄 Outcome
After this lab:
- Dynamic routing is fully implemented
- Network scales easily
- Failover is automatic
- Routing is predictable and controlled

---

## 📌 Next Lab
➡ **Lab 11 – Incident Response & Traffic Analysis**
