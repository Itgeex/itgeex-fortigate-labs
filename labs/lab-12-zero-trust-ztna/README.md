# Lab 12 – Zero Trust & ZTNA Architecture

## 📌 Overview
This lab demonstrates the implementation of a **Zero Trust security model**
using **ZTNA (Zero Trust Network Access)** on FortiGate.

Instead of trusting network location, access decisions are based on:
- User identity
- Device posture
- Application context

---

## 🎯 Objectives
- Understand Zero Trust principles
- Configure ZTNA on FortiGate
- Enforce identity and device-based access
- Replace traditional VPN access for applications
- Monitor and audit Zero Trust access

---

## 🧱 Lab Environment
- FortiGate Firewall
- FortiClient (ZTNA capable)
- Internal applications (Web / RDP)
- Optional: EMS / AD integration

---

## 🧠 Zero Trust Principles

- Never trust, always verify
- Least privilege access
- Continuous verification
- Assume breach

📌 Network location alone is not trusted.

---

## ⚙️ Step 1 – ZTNA Preparation

### 🔧 Requirements
- FortiOS supporting ZTNA
- FortiClient ZTNA Agent
- ZTNA tags (EMS or local)

---

## ⚙️ Step 2 – User & Device Identity

Configure:
- User authentication (Local / LDAP / AD)
- Device posture checks
- ZTNA tags (compliant / non-compliant)

Examples:
- OS version
- Antivirus status
- Device ownership

---

## ⚙️ Step 3 – ZTNA Access Proxy

Navigate to:
`Policy & Objects → ZTNA`

Configure:
- ZTNA access proxy
- Internal application mapping
- External access endpoint

📌 Applications are exposed, not the network.

---

## ⚙️ Step 4 – ZTNA Policies

Create policies based on:
- User identity
- Device posture
- Application

Examples:
- IT Admins → Full access
- Users → Web apps only
- Non-compliant devices → Deny

---

## ⚙️ Step 5 – Security Inspection

Apply:
- IPS
- Antivirus
- Web filtering
- SSL inspection

📌 ZTNA still requires deep inspection.

---

## ⚙️ Step 6 – Monitoring & Visibility

Monitor:
- ZTNA sessions
- User access
- Device compliance

Paths:
- `Log & Report → ZTNA Events`
- Dashboard widgets

---

## 🧪 Step 7 – Validation & Testing

### 🔬 Test Scenarios
- Authorized user on compliant device
- Authorized user on non-compliant device
- Unauthorized user attempt

Expected Results:
- Access allowed or denied correctly
- Policies enforced dynamically
- Events logged

---

## 🔍 Troubleshooting

| Issue | Cause |
|-----|------|
| ZTNA not working | FortiClient version mismatch |
| Access denied | Tag mismatch |
| App unreachable | Proxy misconfiguration |
| No logs | Logging disabled |

---

## 🔐 Best Practices
- Start with pilot apps
- Enforce MFA
- Separate user roles
- Review ZTNA logs regularly
- Gradually replace legacy VPN

---

## 📄 Outcome
After completing this lab:
- Zero Trust architecture is implemented
- Network-level trust is removed
- Application-level access enforced
- Security posture is modern and scalable

---

## 📌 Next Lab
➡ **Lab 13 – Full Enterprise Network Design (End-to-End)**
