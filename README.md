# CodeAlpha_NetworkIntrusionDetectionSystem -  Snort++ Based Network Intrusion Detection System

##  Overview
This project implements a Network Intrusion Detection System (NIDS) using Snort++ (Snort 3) to monitor live network traffic and detect suspicious or malicious activities in real time.

It is developed as part of the CodeAlpha Cyber Security Internship – Task 4 and demonstrates practical intrusion detection using custom rules, protocol inspection, and real-time alert logging.

---

##  Objectives
- Monitor live network traffic passively
- Detect common network attacks and suspicious behaviors
- Generate alerts for intrusion attempts
- Understand real-world IDS configuration and rule writing

---

##  Features
- Real-time packet inspection
- Custom Snort rules (local.rules)
- Detection of:
  - ICMP ping activity
  - TCP SYN port scans
  - SSH brute-force attempts
  - FTP connection attempts
- Protocol inspection (TCP, UDP, ICMP, HTTP, FTP, SSH, DNS, SSL)
- Fast alert logging
- Passive mode operation

---

##  Project Structure
CodeAlpha_NIDS/
│
├── config/
│   ├── snort.lua
│   └── snort_defaults.lua
│
├── rules/
│   ├── local.rules
│   └── file_magic.rules
│
├── logs/
│   └── alert_fast.txt
│
└── README.md

---

##  Technologies Used
- Snort++ (Snort 3.10.0.0)
- Linux (Kali Linux / Ubuntu)
- Lua (Snort configuration)
- PCAP DAQ (Passive Mode)

---

##  Configuration Highlights
- HOME_NET configured to monitor local system traffic
- EXTERNAL_NET set to any external network
- Multiple protocol inspectors enabled:
  - Stream, TCP, UDP, ICMP
  - HTTP / HTTP2
  - FTP / SMTP / SSH
  - DNS / SSL
- Custom rule loading from local.rules

---

##  How to Run
1. Install Snort++
   snort --version

2. Navigate to the project directory
   cd CodeAlpha_NIDS

3. Run Snort in passive mode
   sudo snort -c config/snort.lua -i wlan0 -A alert_fast

   (Replace wlan0 with your active network interface)

---

##  Sample Alerts Detected
- ICMP Ping Detected
- TCP SYN Scan Detected
- SSH Connection Attempt Detected
- Possible SSH Brute Force Attack
- FTP Connection Attempt Detected

Alerts are stored in:
logs/alert_fast.txt

---

##  Testing Performed
- ICMP ping tests
- TCP SYN port scanning
- Repeated SSH login attempts
- FTP connection attempts

All attacks were successfully detected and logged.

---

##  Security Note
This project runs in passive monitoring mode and does not block traffic. It is intended strictly for learning and demonstration purposes.

---

##  Learning Outcomes
- Hands-on experience with Network Intrusion Detection Systems
- Writing and testing custom Snort rules
- Snort++ configuration and tuning
- Understanding real-time security alerts

---

##  Author
Dheekshita R  
Cyber Security Intern – CodeAlpha

---

##  Conclusion
This project demonstrates a fully functional Snort++ based Network Intrusion Detection System capable of detecting multiple network-level attacks in real time. It provides practical exposure to intrusion detection, network security monitoring, and alert analysis.
