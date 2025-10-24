# Portable Intrusion Detection System for Security Information and Event Management

## 📄 Overview
This project presents the design and implementation of a **portable Intrusion Detection and Prevention System (IDPS)** integrated with a **Security Information and Event Management (SIEM)** solution, using open-source tools such as **Wazuh** and **Suricata**.  
The system was deployed in a real network environment to detect vulnerabilities, monitor security events, and respond to potential attacks in real time.

**Author:** Ανδρέας Αυγούστης  
**Supervisors:** Στυλιανός Καραγιάννης, Χριστόφορος Νταντογιάν  
**Institution:** Ιόνιο Πανεπιστήμιο, Τμήμα Πληροφορικής  
**Date:** June 19, 2023

---

## 🧠 Abstract
Wireless network attacks are among the most serious modern cybersecurity threats. This project implements a **portable intrusion detection system** that integrates with a SIEM framework to monitor, detect, and alert for suspicious network activity.  
Using **Wazuh** for centralized log management and **Suricata** for packet analysis, the system automates threat detection and sends alerts via **Slack**. It demonstrates how open-source solutions can enhance network security visibility and proactive defense.

---

## ⚙️ System Architecture
The implemented topology includes:
- **5 Windows systems (victims)**
- **1 Kali Linux system (attacker)**
- **1 Wazuh server** for log collection, analysis, and alerting
- **1 Suricata instance** for intrusion detection and packet analysis
- **Slack integration** for real-time threat notifications

### Components
| Tool | Description |
|------|--------------|
| **Wazuh** | Open-source SIEM providing intrusion detection, file integrity monitoring, and compliance management. |
| **Suricata** | Network IDS/IPS engine used to analyze network packets and detect suspicious patterns. |
| **Agents** | Installed on endpoints for log collection and security event monitoring. |

---

## 🧪 Attack Scenarios
Three main attack simulations were executed:

1. **Network Scan (IP Discovery)**  
   - Tools: `netdiscover`, `nmap`  
   - Identified active IPs, open ports, and services in the network.  
   - Revealed multiple active TCP ports (80, 22, 445, etc.), exposing potential attack surfaces.

2. **Targeted Scanning**  
   - Focused scan on specific IPs (e.g., `192.168.1.142`).  
   - Detected open SSH, HTTPS, and RPC services.  
   - Wazuh identified these as threats and triggered Slack alerts.

3. **SSH Brute Force Attack**  
   - Tool: `nmap --script=ssh-brute.nse`  
   - Simulated credential-based attack on the Wazuh SSH service.  
   - Wazuh classified it as a **level 10 alert** and notified via Slack.

---

## 📈 Results
- The system effectively detected and reported all simulated attacks.  
- TCP-based vulnerabilities were identified as the primary risk vector.  
- Demonstrated successful integration of **Wazuh + Suricata + Slack** for automated monitoring and alerting.

---

## 🔒 Conclusions
- Network security can be enhanced significantly using **open-source IDPS + SIEM** combinations.  
- Real-time alerting and centralized log analysis improve the speed and accuracy of incident response.  
- Further attention should be given to both TCP and UDP vulnerabilities.

---

## 🚀 Future Work
- Full deployment of the system in production for continuous monitoring.  
- Extend monitoring to **Microsoft 365 Cloud services** used by the organization.  
- Develop a **Security Best Practices Guide** to mitigate discovered weaknesses.

---

## 📚 References
1. Yousef Hashem et al., *Endpoint Intrusion Detection and Response Agents in Embedded RAN Products*, 2022.  
2. Fuad Mat Isa et al., *Comprehensive performance assessment on open source intrusion detection systems*, Springer, 2019.  
3. Adabi Raihan Muhammad et al., *Integrated SIEM with IDS for Live Analysis based on Machine Learning*, Procedia Computer Science, 2023.  
4. Rehan Shams et al., *Comparative Analysis Of Intrusion Detection Systems in SDN*, 2023.  
5. Stefan Stanković et al., *A Review of Wazuh Tool Capabilities for Detecting Attacks Based on Log Analysis*, n.d.  
6. Aamna Tariq et al., *Open Source SIEM Solutions for an Enterprise*, Information & Computer Security, 2023.

---

## 🧩 Keywords
`SIEM`, `IDS`, `IPS`, `Wazuh`, `Suricata`, `Network Security`, `Brute Force Attack`, `Slack Integration`, `Open Source`, `Cybersecurity`
