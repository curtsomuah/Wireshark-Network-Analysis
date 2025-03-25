- Overview
This project captures and analyzes network traffic using Wireshark on Ubuntu. The goal is to monitor network activities, understand various protocols, and apply security analysis techniques to detect potential threats.

- Tools Used
Wireshark – Packet capturing and network analysis

Ubuntu Virtual Machine – Environment for testing and capturing traffic

Nmap – Network scanning tool for identifying open ports and services

Curl – HTTP requests to generate network activity

- Steps Taken
1. Installed Wireshark on Ubuntu
sudo apt update
sudo apt install wireshark -y

2.Enabled non-root users to capture packets:
sudo dpkg-reconfigure wireshark-common
sudo usermod -aG wireshark $(whoami)

3.Rebooted the system to apply changes:
sudo reboot

- Captured Live Network Traffic in Wireshark
Opened Wireshark and selected the active network interface (eth0 or wlan0). Clicked Start Capture (blue shark fin button).

- Generated Network Traffic for Analysis
Ran the following commands to create traffic:

Simulated HTTP Requests (Generates HTTP traffic)
curl -I http://girlsgogames.com

Performed a Ping Scan (Generates ICMP traffic)
ping -c 5 nba.com

Performed a DNS Lookup
nslookup facebook.com

Scanned Localhost for Open Ports (Generates TCP & UDP traffic)
sudo nmap -A localhost

- Applied Wireshark Filters to Analyze Specific Protocols

HTTP 
DNS 
ICMP (Ping Traffic)	
TCP 
UDP 
Nmap Scan Detection	
dns.qry.name contains "nba.com"

- Identified Security Risks and Insights
Captured unencrypted HTTP traffic → Found potential security risks from plaintext transmission.

Detected repeated DNS queries → Could indicate malware or beaconing.

Observed TCP Handshakes → Helped understand connection initiation.

Captured ICMP Echo Requests (Pings) → Useful for network troubleshooting and DDoS detection.

Analyzed Nmap scan packets → Identified SYN scan patterns from penetration testing.

📸 Screenshots
Wireshark Packet Captures
✅ Example of HTTP traffic capture:
<img width="1416" alt="Wireshark ss1" src="https://github.com/user-attachments/assets/ec0d00d1-868a-4138-a8d7-0aa0915f033f" />


✅ Example of DNS query analysis:
<img width="1416" alt="Wireshark ss5" src="https://github.com/user-attachments/assets/66ff218f-7794-4eb7-900a-7735a1c88bf6" />
<img width="1416" alt="Wireshark ss2" src="https://github.com/user-attachments/assets/b20ec792-f0ec-4b5a-a117-b15210c94989" />

✅ Example of ICMP (ping) packets:
<img width="1416" alt="Wireshark ss4" src="https://github.com/user-attachments/assets/d7d581ac-cc60-4a8c-bf71-9c837cf45aca" />

✅ Example of TCP SYN scan detected (Nmap scan):
<img width="1416" alt="Wireshark ss3" src="https://github.com/user-attachments/assets/1e15c38d-0b74-432d-8421-2fde0049c6e9" />
