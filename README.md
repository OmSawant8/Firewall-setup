# Firewall-setup
Configuring and testing basic firewall rules to allow or block traffic.
part 1: Firewall Setup and Rule Configuration (Windows/Linux)

Objective
Configure and test basic firewall rules on **Windows** and **Linux (UFW)** to allow or block traffic. This includes:

Blocking a specific port (e.g., Telnet - port 23)
Allowing essential traffic (e.g., SSH - port 22)
Verifying firewall behavior
Cleaning up rules

Windows Firewall (via GUI and PowerShell)
UFW (Uncomplicated Firewall) on Ubuntu Linux


Part 1: Windows Firewall

Steps Followed:

1. **Open Firewall Tool:**
   Start > Search "Windows Defender Firewall with Advanced Security"

2. **List Existing Rules:**
   Click on **Inbound Rules** to view.

3. **Block Telnet (Port 23):**
   Action > New Rule > Port > TCP > Specific local ports: 23
   Block the connection > Apply to all profiles > Name: Block Telnet

4. **Test the Rule:**
    Run: telnet localhost 23 → Should fail to connect.

5. **Remove the Rule:**
   Right-click on the Block Telnet rule > Delete.



Part 2: Linux - UFW (Uncomplicated Firewall)

Commands Used:


Enable UFW if not already
sudo ufw enable

List existing rules
sudo ufw status numbered

Block port 23 (Telnet)
sudo ufw deny 23

Allow SSH (Port 22) to ensure remote access
sudo ufw allow 22

Test blocked port locally
telnet localhost 23  (should fail)
nc -zv localhost 23  

Remove the Telnet block rule
sudo ufw delete deny 23

Final ruleset
sudo ufw status verbose
