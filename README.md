🔐 Firewall Configuration (UFW & iptables)

🛠 Tools Used
- **UFW (Uncomplicated Firewall)** – A beginner-friendly command-line tool for managing firewall rules in Linux.
- **iptables** – A more advanced firewall utility that provides detailed packet filtering and traffic control.
- **OpenSSH Server** – Enables secure remote login to a Linux system over SSH (Port 22).

📄 Description
This project demonstrates how to configure firewall rules in Linux to **allow or block specific ports**, with a focus on SSH (Port 22).  
It covers the following detailed steps:

1. **Installing UFW and OpenSSH Server**  
   - Used `sudo apt install ufw` to install the firewall tool.  
   - Installed `openssh-server` to enable remote SSH access for testing firewall rules.

2. **Listing Current Firewall Rules**  
   - Checked the firewall’s current status with `sudo ufw status`.  
   - Listed active rules and detailed packet counts using `sudo iptables -L -n -v`.

3. **Adding a Rule to Block Inbound Traffic on a Specific Port (Example: Telnet on Port 23)**  
   - Added a block rule with `sudo ufw deny 23/tcp`.  
   - This prevents any incoming TCP traffic on port 23.

4. **Testing the Rule by Attempting to Connect**  
   - Attempted a Telnet connection using `telnet <IP> 23` from a local or remote machine.  
   - Verified that the connection was blocked by the firewall.

5. **Adding a Rule to Allow SSH (Port 22) on Linux**  
   - Used `sudo ufw allow 22/tcp` to permit incoming SSH connections.  
   - Ensured that the SSH service was running with `sudo systemctl enable ssh` and `sudo systemctl start ssh`.

6. **Removing the Test Block Rule to Restore Original State**  
   - Deleted the block rule with `sudo ufw delete deny 23/tcp`.  
   - This restored access to port 23 if needed.

7. **Using iptables for More Granular Control**  
   - Added a rule to accept SSH connections:  
   
     sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
     
   - Checked the iptables rules with:  
     
     sudo iptables -L -n -v | grep 22
     

---

## 🚀 Process Overview
- Install and enable UFW.
- Check and list firewall rules.
- Add, test, and remove block/allow rules for specific ports.
- Use iptables for detailed packet control.
- Verify and reload firewall configurations.

