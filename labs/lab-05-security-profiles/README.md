# Lab 05 – FortiGate Security Profiles (IPS / Antivirus / Web Filtering)

## 📌 Overview
This lab covers the configuration and validation of **FortiGate Security Profiles**
to provide advanced threat protection and content control.

Security Profiles transform FortiGate into a **Next-Generation Firewall (NGFW)**
by inspecting traffic at Layer 7.

---

## 🎯 Objectives
- Configure Intrusion Prevention System (IPS)
- Enable Antivirus (AV) inspection
- Apply Web Filtering policies
- Attach security profiles to firewall policies
- Validate detection and blocking

---

## 🧱 Lab Environment
- FortiGate Firewall
- Internet connectivity
- Client workstation (test traffic source)
- Security Fabric enabled (optional)

---

## 🧠 Security Profiles Strategy

Security Profiles should be:
- Applied only where needed
- Tuned to reduce false positives
- Monitored continuously

📌 Avoid enabling all profiles globally without planning.

---

## ⚙️ Step 1 – Inspection Mode

Navigate to:
`System → Settings`

Choose **Flow-based** or **Proxy-based** inspection.

| Mode | Use Case |
|----|----|
| Flow-based | High performance |
| Proxy-based | Deep inspection |

📌 Proxy-based is recommended for full web & AV inspection.

---

## ⚙️ Step 2 – Antivirus (AV)

### 🔐 AV Profile Configuration
Path:
`Security Profiles → Antivirus`

Enable:
- HTTP
- HTTPS (with SSL inspection)
- FTP
- SMTP / POP3 / IMAP

Actions:
- Block malicious files
- Log all detections

### 🔒 SSL Inspection
- Create SSL Inspection profile
- Use certificate inspection or deep inspection
- Apply to firewall policy

---

## ⚙️ Step 3 – Intrusion Prevention System (IPS)

### 🛑 IPS Profile
Path:
`Security Profiles → Intrusion Prevention`

- Start with **Recommended / Balanced** profile
- Enable:
  - Critical & High severity signatures
- Action:
  - Block
  - Log

📌 Monitor logs to fine-tune IPS signatures.

---

## ⚙️ Step 4 – Web Filtering

### 🌐 Web Filter Profile
Path:
`Security Profiles → Web Filter`

Configure:
- Block malicious categories
- Monitor risky categories
- Allow business-related websites

Examples:
- Block: Malware, Phishing
- Warn: Social Media
- Allow: Business, IT

Enable:
- Safe Search
- FortiGuard Categories

---

## ⚙️ Step 5 – Firewall Policy Integration

Navigate to:
`Policy & Objects → Firewall Policy`

Attach:
- Antivirus Profile
- IPS Profile
- Web Filter Profile
- SSL Inspection Profile

📌 Security Profiles work only when attached to policies.

---

## ⚙️ Step 6 – Logging & Visibility

Enable logging for:
- AV detections
- IPS events
- Web filter blocks

Verify in:
`Log & Report → Security Events`

---

## 🧪 Step 7 – Validation & Testing

### 🔬 Test Scenarios
- Download EICAR test file (AV)
- Access blocked website categories
- Generate known IPS test traffic

Expected Results:
- Threat blocked
- Event logged
- Alert visible in monitoring system

---

## 🔍 Troubleshooting

| Issue | Possible Cause |
|-----|--------------|
| AV not detecting | SSL inspection missing |
| IPS false positives | Signature too aggressive |
| Web filter bypass | Policy order issue |
| Performance drop | Inspection mode mismatch |

Useful CLI:
diagnose debug application ipsmonitor -1
diagnose test application antivirus 99

---

## 🔐 Best Practices
- Start with FortiGuard recommended profiles
- Tune gradually
- Enable logging before blocking
- Review reports regularly
- Monitor performance impact

---

## 📄 Outcome
After this lab:
- Traffic is inspected at Layer 7
- Malware & intrusions are blocked
- Web usage is controlled
- Firewall operates as NGFW

---

## 📌 Next Lab
➡ **Lab 06 – FortiGate Hardening & Security Baseline**
