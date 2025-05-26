# nmap-port-scan
 Cyber Security Internship – Task 1 Report
📌 Task Title:
Scan Your Local Network for Open Ports

🎯 Objective
To use Nmap for scanning devices in the local network to identify open ports and understand potential security risks. This task demonstrates basic network reconnaissance and security assessment.

🛠 Tools Used
Nmap 7.97 – For port scanning.

Command Prompt (Windows) – For executing Nmap commands.

Wireshark (Optional) – Not used in this scan, but useful for packet analysis.

GitHub – For documentation and submission.

🌐 Network Details
Scanned IP Address: 192.168.31.89

Target Device: LAPTOP-QB83HU7I.lan

⚙️ Scan Command Used
bash
Copy
Edit
nmap -sS 192.168.31.89
The -sS flag performs a TCP SYN scan (also called a "half-open scan"), which is fast and stealthy.

📊 Scan Results Summary
pgsql
Copy
Edit
Host: LAPTOP-QB83HU7I.lan (192.168.31.89)
Host is up (0.000010s latency).
Not shown: 996 closed tcp ports (reset)
PORT     STATE SERVICE
135/tcp  open  msrpc
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
1521/tcp open  oracle
🔍 Analysis of Open Ports
Port	Service	Description	Potential Risks
135	msrpc	Microsoft RPC service, used by Windows for inter-process communication	Exploitable in older Windows versions (DCOM exploits)
139	netbios-ssn	NetBIOS Session Service, used for file sharing over a LAN	Susceptible to information disclosure attacks
445	microsoft-ds	Direct SMB over TCP/IP (file/printer sharing)	Targeted by malware like WannaCry
1521	oracle	Oracle database listener port	Could allow access to Oracle DB if misconfigured

🧠 Key Learnings
Open ports reveal services running on a device which can be exploited if not secured properly.

Port scanning is a critical step in both defense (network assessment) and offense (attacker reconnaissance).

SMB and NetBIOS ports (139/445) are common targets for lateral movement within networks.

Nmap's TCP SYN scan is effective for identifying open TCP ports quickly and with minimal detection risk.

🔐 Security Recommendations
Close unused ports via firewall rules or system configurations.

Restrict SMB and NetBIOS traffic within secure VLANs or only to trusted devices.

Regularly update services (e.g., Oracle DB, Windows RPC) to prevent exploits.

Use a firewall to monitor and control incoming/outgoing traffic.

