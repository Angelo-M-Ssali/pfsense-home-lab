# pfsense-home-lab
This is a simple pfSense firewall home lab setup guide
# pfSense Home Lab Firewall Setup Guide

This guide outlines the basic steps I followed to set up a secure home lab environment using pfSense as the firewall and router. The goal was to simulate an enterprise-grade security solution and strengthen my practical cybersecurity skills.

---

## 🛠️ Tools and Environment

- **pfSense** (open-source firewall and router)
- **VirtualBox** (for virtualization)
- **Kali Linux** / **Ubuntu** (for testing)
- **Snort** (Intrusion Detection System)
- **Nmap / Nessus** (for vulnerability scanning)

---

## 🔧 Basic Setup Steps

1. **Download pfSense**  
   - Visit [pfSense official site](https://www.pfsense.org/download/) and download the latest ISO installer.

2. **Create Virtual Machine in VirtualBox**  
   - Create a new VM with at least 1GB RAM and 2 virtual NICs (one for WAN, one for LAN).
   - Attach the pfSense ISO to the VM.

3. **Install pfSense**  
   - Boot the VM and follow the installer wizard to complete the installation.
   - Set up the LAN and WAN interfaces during the wizard.

4. **Access pfSense Web GUI**  
   - Connect to the LAN IP from your host system’s browser (default: `https://192.168.1.1`).
   - Log in with default credentials (`admin` / `pfsense`).

5. **Basic Configuration**  
   - Change the default admin password.  
   - Set up DHCP for the LAN interface if needed.  
   - Configure basic WAN settings (static or DHCP).

6. **Firewall Rules and NAT**  
   - Create rules to block unnecessary inbound traffic and only allow trusted connections.
   - Set up NAT if needed to route internal traffic.

7. **Install Snort (IDS)**  
   - Navigate to `System > Package Manager` and install Snort.
   - Configure Snort rulesets to detect suspicious activity.

8. **Testing and Validation**  
   - Use Kali Linux VM or other tools to simulate network scans (e.g., Nmap) to validate firewall rules.
   - Fine-tune Snort alerts to reduce false positives.

9. **Periodic Audits**  
   - Regularly review logs (`Status > System Logs`) and adjust firewall rules as needed.
   - Document rule changes and network architecture updates.

---

## 🪛 Troubleshooting

- **pfSense Web GUI not accessible**  
  - Double-check that the LAN interface has the correct IP address.  
  - Verify your VirtualBox network adapter settings (set to “Internal Network” or “Bridged” as needed).  
  - Try using `https://192.168.1.1` from another VM or host OS.

- **No internet access from VMs behind pfSense**  
  - Check the firewall rules to ensure outbound traffic is allowed from the LAN interface.  
  - Verify the NAT configuration is correct (`Firewall > NAT`).  
  - Ensure the pfSense VM’s WAN interface is getting an IP from your host’s network (DHCP or static).

- **Snort not generating alerts**  
  - Ensure Snort is properly configured with active rulesets.  
  - Test with known exploits or Nmap scans to see if alerts trigger.  
  - Check Snort logs under `Services > Snort > Alerts`.

- **Slow network performance**  
  - Allocate more RAM/CPU to the pfSense VM if possible.  
  - Limit the number of active rules in Snort to reduce resource load.  
  - Optimize VirtualBox adapter settings (e.g., use “Paravirtualized Network” for better performance).

---

## 📌 Key Skills Practiced

✅ Network segmentation and isolation  
✅ Firewall configuration and hardening  
✅ Intrusion detection and monitoring  
✅ Basic vulnerability scanning  
✅ Documentation and change management

---

## 🚀 Future Enhancements

- Integrate **VPN** for remote secure access  
- Deploy **Suricata** as an alternative IDS/IPS  
- Expand lab with **Windows Server** and domain controller for AD testing

---

## 📄 Disclaimer

This project was conducted in a controlled home lab environment for **educational purposes** only. Please do not use these configurations for real-world production environments without proper assessment and compliance review.

---

**Thank You For Stopping By!** 🎉  
