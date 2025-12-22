# Lab 09 – FortiGate SSL VPN & User-Based Access Control

## 📌 Overview
This lab demonstrates how to configure **SSL VPN** on FortiGate and apply
**user-based access control** using identity-aware firewall policies.

The goal is to provide **secure remote access** while enforcing
role-based and least-privilege access.

---

## 🎯 Objectives
- Configure FortiGate SSL VPN
- Integrate local or directory-based users
- Apply role-based access control (RBAC)
- Enforce user-based firewall policies
- Monitor and audit VPN user activity

---

## 🧱 Lab Environment
- FortiGate Firewall
- Internet connectivity
- Remote client (FortiClient)
- Optional: Active Directory / LDAP

---

## 🧠 SSL VPN Design Principles
- Identity-aware access
- Least privilege
- Secure authentication
- Visibility and auditability

📌 VPN users should access **only what they need**.

---

## ⚙️ Step 1 – User & Authentication Setup

### 👤 User Creation
Path:
`User & Authentication → User Definition`

Options:
- Local users
- LDAP / Active Directory users

Enable:
- Strong password policy
- Two-Factor Authentication (2FA)

---

## ⚙️ Step 2 – User Groups

Create user groups:
- IT_Admins
- Remote_Users
- Vendors (restricted access)

📌 Policies will be applied to groups, not individual users.

---

## ⚙️ Step 3 – SSL VPN Configuration

Navigate to:
`VPN → SSL-VPN Settings`

Configure:
- Listening interface (WAN)
- Port (default: 443 or custom)
- IP pool for VPN users
- Split tunnel or full tunnel

---

## ⚙️ Step 4 – SSL VPN Portals

Create multiple portals:
- Full Access (IT Admins)
- Restricted Access (Users)
- Web-only (Vendors)

Configure:
- Allowed subnets
- Bookmark access
- Tunnel mode settings

---

## ⚙️ Step 5 – Firewall Policy (User-Based)

Navigate to:
`Policy & Objects → Firewall Policy`

Create policies:
- SSL-VPN → Internal networks
- Apply user group restrictions
- Enable logging

📌 Identity-based policies replace IP-only controls.

---

## ⚙️ Step 6 – Security Hardening

- Enable 2FA for VPN users
- Restrict admin access via VPN
- Disable weak encryption
- Enable login attempt limits

---

## ⚙️ Step 7 – Monitoring & Logging

Monitor:
- VPN connections
- User login/logout
- Traffic per user

Paths:
- `Log & Report → VPN Events`
- `Dashboard → SSL VPN`

---

## 🧪 Step 8 – Validation & Testing

### 🔬 Test Scenarios
- User login success/failure
- Group-based access restriction
- Unauthorized network access attempt

Expected Results:
- Correct portal assignment
- Access limited by user role
- Events logged correctly

---

## 🔍 Troubleshooting

| Issue | Cause |
|-----|------|
| Login failed | Auth method mismatch |
| No access after login | Missing firewall policy |
| Split tunnel not working | Routing issue |
| 2FA not prompting | Token misconfiguration |

Useful CLI:
diagnose debug application sslvpn -1
diagnose debug enable

---

## 🔐 Best Practices
- Always use user groups
- Enable MFA for remote access
- Log all VPN activity
- Use separate portals per role
- Review VPN users regularly

---

## 📄 Outcome
After completing this lab:
- Secure remote access is implemented
- Access is identity-aware
- Least-privilege enforced
- VPN activity is auditable

---

## 📌 Next Lab
➡ **Lab 10 – Advanced Routing (OSPF / BGP)**
