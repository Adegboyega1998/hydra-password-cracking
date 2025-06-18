# 🔐 Hydra SSH Brute-Force Attack on Cowrie Honeypot

This project simulates a brute-force password attack using Hydra on a vulnerable SSH service provided by the Cowrie honeypot. It’s part of my hands-on cybersecurity journey, focusing on Red Team (offensive) techniques.

## 📁 Project Structure

hydra-password-cracking/
│
├── README.md # Project overview (this file)
├── setup.md # Full step-by-step setup instructions
├── analysis.md # Summary and key learnings from the project
├── passwords.txt # Custom password list used for brute-force
└── screenshots/ # Screenshot documentation
├── 01_hydra_project_folder_created.png
├── 02_passwords_txt_created.png
├── 03_hydra_attack_success.png
└── 04_cowrie_log_verified.png


## 🛠 Tools Used

- Kali Linux (Attacker VM)
- Ubuntu Server with Cowrie (Target VM)
- Hydra (Brute-force tool)
- VirtualBox

## 🎯 Objective

To demonstrate how Hydra can perform a dictionary-based SSH brute-force attack against a honeypot and document the results captured by Cowrie.

## 📸 Screenshots Preview

| Step | Screenshot Name                          | Description                          |
|------|------------------------------------------|--------------------------------------|
| 1    | 01_hydra_project_folder_created.png       | Hydra project directory initialized  |
| 2    | 02_passwords_txt_created.png              | Password wordlist file created       |
| 3    | 03_hydra_attack_success.png               | Successful brute-force attack result |
| 4    | 04_cowrie_log_verified.png                | Cowrie logs showing captured attack  |

## 🔚 Outcome

This project shows how attackers use tools like Hydra to guess credentials and how honeypots like Cowrie can log and analyze those attempts.









