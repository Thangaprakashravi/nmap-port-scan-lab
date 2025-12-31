# nmap-port-scan-lab

🧪 LAB RECORD (ONLY PORT SCANNING)
📌 Title

Detection of Nmap Port Scanning Using UFW Firewall on Ubuntu Linux

🎯 Aim

To perform a port scan using Nmap from Kali Linux and detect the scan using UFW firewall logs on Ubuntu Linux.

🖥️ Lab Setup
Attacker Machine

OS: Kali Linux

Tool: Nmap

Target Machine

OS: Ubuntu Linux

Firewall: UFW

Log file: /var/log/ufw.log

🌐 Network Details
Machine	IP Address
Kali Linux	192.168.1.2
Ubuntu Linux	192.168.1.50

(Network type: Bridged Adapter)

🧪 Procedure
Step 1: Enable UFW Logging (Ubuntu)
sudo ufw enable
sudo ufw logging high

Step 2: Block Port 80 (Ubuntu)
sudo ufw deny from 192.168.1.2 to any port 80 proto tcp
sudo ufw reload

Step 3: Monitor Logs (Ubuntu)
sudo tail -f /var/log/ufw.log | grep 192.168.1.2

Step 4: Perform Port Scan (Kali)
sudo nmap -Pn -p80 192.168.1.50

🔍 Output (Kali)
80/tcp filtered http

📄 Sample Log Entry (Ubuntu)
UFW BLOCK IN=enp0s3 SRC=192.168.1.2 DST=192.168.1.50
PROTO=TCP SPT=52341 DPT=80 SYN

✅ Result

The port scanning activity was successfully detected and logged on the Ubuntu system using UFW firewall.

📌 Conclusion

Port scanning attempts can be effectively detected by enabling firewall logging. This helps in identifying early reconnaissance attacks.

👤 Author

Thangaprakash
