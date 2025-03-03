# TryHackMe - Tutorial Machine Documentation

This document provides a comprehensive guide for setting up and completing the **Tutorial** machine on TryHackMe. The process includes configuring the VPN, securing the connection, and performing the required steps to complete the challenge.

## Table of Contents

1. Prerequisites
2. Repository Structure
3. Step 1: Setting Up TryHackMe VPN
4. Step 2: Securing Your Connection
5. Step 3: Accessing and Completing the Challenge
6. Validation and Testing
7. Conclusion and Additional Resources

---

## 1. Prerequisites

### Software and Hardware Requirements:
- **Operating System:** Kali Linux or Parrot Security OS.
- **Network Access:** Internet connection to access TryHackMe.
- **TryHackMe Account:** A registered account on [TryHackMe](https://tryhackme.com/).

### Required Tools:
- SSH access to the machine.
- Basic packages: `nano`, `openvpn`.

### Cloning the Repository
To access the scripts and documentation, clone this GitHub repository:

```bash
git clone https://github.com/fartaviao/tryhackme-tutorial.git
cd tryhackme-tutorial
```

---

## 2. Repository Structure

```
tryhackme-tutorial/
├── README.md                      # Introduction and overview
├── tutorial.md                    # Main Documentation
├── tutorial-write-up.pdf          # Write up
├── Scripts/
│   ├── safevpn-thm.sh             # Security script for VPN
└── Screenshots/                   # Visual references
    ├── Screenshot-01.png
    ├── Screenshot-02.png
    ├── Screenshot-03.png
    ├── Screenshot-04.png
    ├── Screenshot-05.png
    ├── Screenshot-06.png
    ├── Screenshot-07.png
    ├── Screenshot-08.png
    ├── Screenshot-09.png
    └── Screenshots.md
    
```

---

## 3. Step 1: Setting Up TryHackMe VPN

The first step is to establish a secure connection with the TryHackMe platform using OpenVPN.

### Steps:

## Access TryHackMe and Join the Tutorial Machine
1. **Log in to TryHackMe:**
   - Visit [TryHackMe](https://tryhackme.com/) and log in.
2. **Join the Tutorial Machine:**
   - Search for the *room* named **Tutorial**.
   - Click on **Join Room** to participate.
   - Then click on **Start Machine** (wait around 1 min to the target IP)
   
---
## Download the VPN Configuration File
To connect to TryHackMe machines, we need a **VPN**. Follow these steps:
1. **Access the VPN settings:**
   - Click on your **profile** at the top-right corner of TryHackMe.
   - Select **Access**.
2. **Download the configuration file:**
   - In the VPN section, choose **Download My Configuration File**.
   - The file with the `.ovpn` extension will be downloaded to your `Downloads` folder.

---
## Connect Kali Linux or Parrot Security to TryHackMe via VPN
1. **Open a terminal.**
2. **Navigate to the folder where the file was downloaded:**
   ```bash
   cd ~/Downloads
   ls
   ```
   - You should see a file with the `.ovpn` extension (e.g., `<youruser.ovpn>` with the name of your user).
3. **For be more organized we can crete the following structure ~/Downloads/TryHackMe/Tutorial/OpenVPN**
   ```bash
   mkdir -p TryHackMe/Tutorial/OpenVPN
   ls -R TryHackMe
   ```
   - Move the .ovpn file to the OpenVPN location
   ```bash
   mv youruser.ovpn TryHackMe/Tutorial/OpenVPN
   cd TryHackMe/Tutorial/OpenVPN
   ls
   ```
4. **Run the following command to connect to the VPN:**
   ```bash
   sudo openvpn <youruser.ovpn>
   ```
   - Enter your password when prompted.
   - If the connection is successful, you will see a message indicating that a new network interface `tun0` has been created.
   - Do not close this terminal to the VPN can work (if you want to finish it press Ctrl + c)

## Verify Connectivity with the TryHackMe Machine
1. **Open a new terminal and run:**
   ```bash
   ip a
   ```
   - Look for the `tun0` interface, which should have an assigned IP address.
2. **Check the connection to the machine:**
   - Find the machine's IP address on TryHackMe.
   - Run a ping test:
     ```bash
     ping -c4 <MACHINE_IP>
     ```
   - If you receive responses, it means the VPN is working correctly.

---
## 4. Step 2: Securing Your Connection
For security reasons, we can restrict our machine's access to only the machine of TryHackMe VPN using `iptables`.

1. **Download the security script:**
   - Get the "Wh1teDrvg0n" Script on GitHub to ensure security in your network:
   - Open a browser and search for *White Dragon VPN Safe* on Google.
   - Download the script from `safevpn-thm.sh` on GitHub.
2. **Move the script to the working folder**
   ```bash
   cd ~/Downloads
   mv safevpn-thm.sh TryHackMe/Tutorial/OpenVPN
   cd TryHackMe/Tutorial/OpenVPN
   ls
   ```
2. **Grant execution permissions to the script:**
   ```bash
   sudo chmod +x safevpn-thm.sh
   ```
3. **Run the script to configure firewall rules:**
   ```bash
   sudo ./safevpn-thm.sh <MACHINE_IP>
   ```
   - This will restrict incoming and outgoing connections only to TryHackMe's VPN.

---

## 5. Step 3: Access the Machine and Complete the Challenge
1. **Open a browser in Kali Linux or Parrot Security.**
2. **Enter the machine's IP address in the address bar.**
3. **Find the *flag* on the web page.**
4. **Copy the *flag* and paste it into TryHackMe.**
5. **Click *Submit* to complete the machine.**

---

## 6. Validation and Testing

1. **Verify VPN Connection:**
   ```bash
   ip a | grep tun0
   ```
2. **Test Connectivity to the Target Machine:**
   ```bash
   ping -c 4 <MACHINE_IP>
   ```
3. **Check Firewall Rules:**
   ```bash
   sudo iptables -L
   ```

---

## 7. Conclusion and Additional Resources

### Summary
With this guide, you have successfully connected to TryHackMe via VPN, secured your connection, and completed the Tutorial machine.

### Recommended Resources:
- TryHackMe Official Documentation → [https://tryhackme.com/](https://tryhackme.com/)
- OpenVPN Documentation → [https://openvpn.net/](https://openvpn.net/)
- TryHackMe safe VPN access → [https://github.com/Wh1teDrvg0n/safeVPN-THM](https://github.com/Wh1teDrvg0n/safeVPN-THM)

### Security Considerations
- Always **disconnect the VPN** after finishing a session.
- Use **firewall rules** to prevent unauthorized access.

### Contributions
Contributions are welcome! Feel free to fork the repository, make improvements, and submit a pull request.

---

© 2024 Fausto Artavia Ocampo
Happy hacking! 🚀
