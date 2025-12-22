# Lab 11 – FortiGate Incident Response & Traffic Analysis

## 📌 Overview
This lab focuses on **detecting, analyzing, and responding to security incidents**
using FortiGate logs, traffic analysis, and security events.

The objective is to build a **structured incident response workflow**
based on real-world attack scenarios.

---

## 🎯 Objectives
- Detect security incidents
- Analyze traffic and logs
- Identify attack patterns
- Contain and mitigate threats
- Document incidents for auditing

---

## 🧱 Lab Environment
- FortiGate Firewall
- Centralized logging (FortiAnalyzer / Syslog)
- Internal clients and servers
- Simulated attack traffic

---

## 🧠 Incident Response Lifecycle

1. Detection  
2. Analysis  
3. Containment  
4. Eradication  
5. Recovery  
6. Lessons Learned  

📌 Logs are the backbone of incident response.

---

## ⚙️ Step 1 – Incident Detection

### 🔔 Detection Sources
- IPS alerts
- Antivirus detections
- Anomalous traffic patterns
- Admin login failures
- VPN abuse

Tools:
- FortiGate Dashboard
- FortiAnalyzer
- Monitoring alerts (PRTG)

---

## ⚙️ Step 2 – Traffic Analysis

Analyze:
- Source & destination IPs
- Ports & protocols
- Session duration
- Application type

Paths:
- `Log & Report → Traffic Log`
- `Security Events`

📌 Identify **who**, **what**, **when**, **how**.

---

## ⚙️ Step 3 – Threat Classification

Classify incidents:
- Malware infection
- Brute-force attack
- Port scanning
- Data exfiltration attempt
- Policy violation

Assign severity:
- Low / Medium / High / Critical

---

## ⚙️ Step 4 – Containment

Immediate actions:
- Block source IP
- Quarantine infected host
- Disable compromised user
- Shut down affected policy

📌 Containment first, investigation second.

---

## ⚙️ Step 5 – Eradication & Mitigation

- Update IPS / AV signatures
- Patch vulnerable systems
- Harden affected policies
- Enable additional security profiles

---

## ⚙️ Step 6 – Recovery

- Restore services
- Monitor for reoccurrence
- Validate traffic normalization

---

## ⚙️ Step 7 – Documentation & Reporting

Document:
- Timeline
- Root cause
- Impacted systems
- Mitigation steps

Generate:
- Incident report
- Management summary

📌 Documentation is mandatory for audits.

---

## 🧪 Step 8 – Validation & Simulation

### 🔬 Test Scenarios
- Simulate malware download
- Generate port scan
- Failed VPN login attempts

Expected Results:
- Incident detected
- Alert generated
- Response applied
- Logs preserved

---

## 🔍 Troubleshooting

| Issue | Cause |
|-----|------|
| No alert | Profile not applied |
| Logs missing | Logging disabled |
| False positives | Over-aggressive profiles |
| No visibility | SSL inspection missing |

---

## 🔐 Best Practices
- Centralize logs
- Define IR playbooks
- Automate where possible
- Review incidents regularly
- Train response procedures

---

## 📄 Outcome
After completing this lab:
- Security incidents are detectable
- Traffic analysis is actionable
- Response is structured
- Environment is SOC-ready

---

## 📌 Next Lab
➡ **Lab 12 – Zero Trust & ZTNA Architecture**
