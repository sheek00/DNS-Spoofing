# DNS Spoofing using Python 2.7, Scapy & NetfilterQueue

## 📌 Description
This project demonstrates a DNS Spoofing attack using Python 2.7, Scapy, and NetfilterQueue.  
The script intercepts DNS packets and replaces the real IP with a spoofed IP, redirecting the victim to the attacker's machine.  
⚠️ For lab use ONLY.

## 🧠 How It Works
1. Victim sends a DNS request (e.g., www.httpforever.com)
2. iptables forwards DNS packets to NetfilterQueue
3. The Python script inspects DNS responses
4. If the domain matches, the DNS answer is modified
5. Victim receives a spoofed IP instead of the real one

## 🛠 Requirements
- Python 2.7  
- Scapy (compatible with Python2)  
- NetfilterQueue  
- iptables  

Install dependencies:
sudo apt-get update
sudo pip install scapy
sudo pip install NetfilterQueue


## 🔥 iptables Rules
Forward DNS packets to the queue:

sudo iptables -I INPUT -j NFQUEUE --queue-num 0

sudo iptables -I OUTPUT -j NFQUEUE --queue-num 0

Reset rules:
sudo iptables --flush


## ▶️ How to Run
sudo python DNS_Spoofer.py

Test with:
ping -c 1 www.httpforever.com

A successful attack returns the attacker’s IP.

## 🛡 Legal Notice
DNS spoofing without authorization is illegal.  
Use ONLY inside your own lab environment.

## 👤 Author
Mohammed Alsheikh  
Junior Cybersecurity Engineer | Offensive Security Learner | Python Automation Builder
