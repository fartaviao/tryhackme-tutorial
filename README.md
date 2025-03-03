<img src="https://raw.githubusercontent.com/fartaviao/fartaviao/refs/heads/main/Banner%20Fausto.jpg" alt="Banner Fausto Artavia Ocampo">

# TryHackMe - Tutorial Machine Documentation

## Overview
This repository contains detailed documentation on how to connect a **Kali Linux or Parrot Security** machine to **TryHackMe** via VPN and complete the **Tutorial** machine. 

## Contents
- **Step-by-step guide** to set up a VPN connection.
- **Instructions** on how to verify connectivity.
- **Security measures** to restrict access using `iptables`.
- **Steps to complete the tutorial challenge**.

## Repository Structure

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

## Getting Started
To follow this guide, ensure you have:
- A **TryHackMe** account ([Sign up here](https://tryhackme.com/)).
- A machine or VM with **Kali Linux** or **Parrot Security**.
- An active internet connection.

## Documentation and Screenshots
For detailed documentation and step-by-step guide, refer to the [Main Documentation](https://github.com/fartaviao/tryhackme-tutorial/blob/main/Tutorial.md)
as well you can check the [Screenshots](https://github.com/fartaviao/tryhackme-tutorial/blob/main/Screenshots/Screenshots.md) for better clarity of the process.

You also can access the full Write Up document here [Write Up](https://github.com/fartaviao/tryhackme-tutorial/blob/main/tutorial-write-up.pdf)

## How to Use This Repository
1. Clone this repository:
   ```bash
   git clone https://github.com/fartaviao/tryhackme-tutorial.git
   ```
2. Navigate to the repository folder:
   ```bash
   cd tryhackme-tutorial
   ```
3. Open `tutorial.md` to follow the steps.

## License
This documentation is provided for **educational purposes**. Feel free to modify and use it as needed.

### Recommended Resources:
- TryHackMe Official Documentation → [https://tryhackme.com/](https://tryhackme.com/)
- OpenVPN Documentation → [https://openvpn.net/](https://openvpn.net/)
- TryHackMe safe VPN access → [https://github.com/Wh1teDrvg0n/safeVPN-THM](https://github.com/Wh1teDrvg0n/safeVPN-THM)

### Security Considerations
- Always **disconnect the VPN** after finishing a session.
- Use **firewall rules** to prevent unauthorized access.

---

## Author
Created by **Fausto Artavia Ocampo** for educational use and cybersecurity training.

Happy hacking! 🚀
