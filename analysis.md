# 🔍 Project Analysis – SSH Password Cracking with Hydra

## 🧪 Summary

This project demonstrates how brute-force SSH password attacks are carried out using **Hydra**, a popular penetration testing tool.  
We simulated a real-world attack against a **Cowrie honeypot**, which was listening on port `2222`. Hydra attempted multiple password guesses using a wordlist, and Cowrie logged each attempt.

---

## 🎯 Objectives

- Understand how brute-force attacks work using Hydra
- Generate a custom password wordlist
- Run Hydra against Cowrie’s fake SSH service
- Analyze how Cowrie logs failed and successful login attempts
- Practice red team (offensive) and blue team (defensive) thinking

---

## 🧰 Tools Used

- Kali Linux (attacker system)
- Hydra (password cracking tool)
- Ubuntu Server running Cowrie (honeypot)
- VirtualBox
- Git & GitHub

---

## 🔐 Hydra Command Used

```bash
hydra -l root -P passwords.txt ssh://192.168.40.83:2222
```

This command instructed Hydra to:
- Use `root` as the login username
- Use `passwords.txt` (a custom 5-password wordlist) for brute-force attempts
- Target the SSH service on the honeypot IP at port 2222

---

## 📄 Cowrie Log Output

Sample lines captured by Cowrie:

```text
HoneyPotSSHTransport,root trying auth b'password'
HoneyPotSSHTransport,root authenticated with b'password'
HoneyPotSSHTransport,root logging out
HoneyPotSSHTransport,session connection lost after 0.1 seconds
```

Cowrie logs every login attempt and interaction, even though the system is fake. These logs provide insight into the attacker’s behavior.

---

## 🧠 What I Learned

- Brute-force attacks are fast and easy to launch using Hydra.
- Cowrie logs attacker attempts in detail, including IP, username, and password.
- Even when a password is "accepted," Cowrie isolates the attacker in a fake shell.
- Honeypots help defenders observe red team behavior safely.
- Combining attack simulation with log analysis builds both red and blue team skills.

---

## ✅ Conclusion

This project gave me hands-on experience with both:
- Offensive techniques (Hydra password cracking)
- Defensive monitoring (Cowrie honeypot logging)

By simulating an attack and analyzing the logs, I better understand the real-world risk of poor passwords and the value of intrusion detection systems.
