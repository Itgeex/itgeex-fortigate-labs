# Lab 07 – FortiGate Monitoring, Logging & Alerting

## 📌 Overview
This lab focuses on **monitoring, logging, and alerting** for FortiGate
firewalls in enterprise environments.

The objective is to gain **visibility, traceability, and operational awareness**
to detect issues, security events, and performance problems early.

---

## 🎯 Objectives
- Enable and verify FortiGate logging
- Integrate FortiGate with monitoring platforms
- Configure alerts for critical events
- Analyze logs for troubleshooting and security incidents
- Apply monitoring best practices

---

## 🧱 Lab Environment
- FortiGate Firewall (Standalone or HA)
- Monitoring system (PRTG / Syslog Server / FortiAnalyzer)
- Internal & Internet traffic sources

---

## 🧠 Monitoring Strategy
Effective monitoring answers:
- Is the firewall **up and healthy**?
- Is traffic flowing as expected?
- Are there **security events**?
- Can incidents be **traced and audited**?

---

## ⚙️ Step 1 – Enable Local & Remote Logging

### 🔐 Logging Settings
Navigate to:  
`Log & Report → Log Settings`

- Enable:
  - Forward Traffic logs
  - VPN events
  - System events
  - Admin activity logs
- Set log severity appropriately

📌 Local disk logging is useful, but **remote logging is mandatory** in production.

---

## ⚙️ Step 2 – Syslog Integration

### 📡 Configure Syslog Server
- Log Type: Event & Traffic
- Protocol: UDP / TCP
- Port: `514`
- Source IP: FortiGate management IP

### 📊 Log Types to Forward
- Traffic
- VPN
- System
- Security events

📌 Use TCP if reliability is required.

---

## ⚙️ Step 3 – FortiAnalyzer (Optional but Recommended)

### 📘 Benefits
- Centralized logging
- Advanced search & reporting
- Compliance-ready auditing
- Historical traffic analysis

### 🔧 Integration
- Register FortiGate to FortiAnalyzer
- Verify log reception
- Enable analytics

---

## ⚙️ Step 4 – PRTG Monitoring Integration

### 📊 Monitor Key Metrics
- Interface bandwidth usage
- CPU & memory utilization
- Session count
- VPN tunnel status
- HA cluster status

📌 Monitor symptoms, not just device status.

---

## ⚙️ Step 5 – Alerting & Notifications

### 🚨 Critical Alerts
Configure alerts for:
- FortiGate down
- HA failover
- VPN tunnel down
- High CPU / memory usage
- Admin login failures

### 📧 Notification Channels
- Email
- SNMP traps
- Monitoring system alerts

---

## ⚙️ Step 6 – Dashboard & Visibility

### 📈 Built-in Dashboards
- Security events overview
- Top sources & destinations
- VPN status
- System health

### 📊 Custom Dashboards
- Focus on business-critical traffic
- Track anomalies and spikes

---

## 🧪 Step 7 – Validation & Testing

### 🔍 Test Scenarios
- Generate test traffic
- Bring down WAN interface
- Force HA failover
- Simulate VPN outage

Expected Results:
- Events logged
- Alerts triggered
- Monitoring dashboards updated

---

## 🔍 Troubleshooting

| Issue | Possible Cause |
|------|---------------|
| No logs | Logging disabled |
| Missing traffic logs | Policy logging disabled |
| Alerts not triggered | Thresholds misconfigured |
| Delay in logs | UDP packet loss |

Useful CLI commands:
diagnose log test
execute log filter category event

---

## 🔐 Monitoring Best Practices
- Centralize logs
- Define alert thresholds carefully
- Avoid alert fatigue
- Retain logs per compliance requirements
- Review dashboards regularly

---

## 📄 Outcome
At the end of this lab:
- FortiGate is fully monitored
- Logs are centralized and searchable
- Alerts provide operational awareness
- Environment is audit-ready

---

## 📌 Next Lab
➡ **Lab 08 – SD-WAN & Multi-WAN Configuration**
