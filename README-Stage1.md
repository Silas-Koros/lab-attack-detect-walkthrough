# Stage 1 — Lab Setup (Kali → Windows → Ubuntu)

**Purpose:**  
Build a safe, isolated VMware lab and verify that the virtual machines (VMs) can communicate with each other.  
This is the foundation for later Attack + Detect stages.

---

## 🌐 Network and VMs

- Network: **Host-only (VMnet1)** — `172.16.94.0/24` (no gateway)
- IP addresses:
  - **Kali (attacker):** `172.16.94.128`
  - **Ubuntu (log/detection):** `172.16.94.131`
  - **Windows 10 Pro x64 (target):** `172.16.94.133`

---

## 📁 What this stage includes
- `infra/vm_specs.md` — VM names, specs, IPs, and snapshots  
- `artifacts/screenshots/` — proof screenshots (IPs, pings, VMnet)  

---

### Screenshots (click to enlarge)
<p align="left">
  <a href="artifacts/screenshots/Diagram.png"><img src="artifacts/screenshots/Diagram.png" width="220"></a>
  <a href="artifacts/screenshots/Kali_ip.png"><img src="artifacts/screenshots/Kali_ip.png" width="220"></a>
  <a href="artifacts/screenshots/Ubuntu_ip.png"><img src="artifacts/screenshots/Ubuntu_ip.png" width="220"></a>
</p>
<p align="left">
  <a href="artifacts/screenshots/Windows_ip.png"><img src="artifacts/screenshots/Windows_ip.png" width="220"></a>
  <a href="artifacts/screenshots/Verify_ping.png"><img src="artifacts/screenshots/Verify_ping.png" width="220"></a>
</p>

---


## 🧩 Commands used (from Kali)

```bash
# list network interfaces
ip a

# check routing table
ip r

#!/bin/bash
# verify_connectivity.sh - run from Kali
targets=(172.16.94.131 172.16.94.133)
for ip in "${targets[@]}"; do
  echo "Pinging $ip ..."
  ping -c 4 $ip
done
---

### Screenshots (click to enlarge)
<p align="left">
  <a href="artifacts/screenshots/stage1_diagram.png"><img src="artifacts/screenshots/stage1_diagram.png" width="220"></a>
  <a href="artifacts/screenshots/stage1_kali_ip.png"><img src="artifacts/screenshots/stage1_kali_ip.png" width="220"></a>
  <a href="artifacts/screenshots/stage1_ubuntu_ip.png"><img src="artifacts/screenshots/stage1_ubuntu_ip.png" width="220"></a>
</p>
<p align="left">
  <a href="artifacts/screenshots/stage1_windows_ip.png"><img src="artifacts/screenshots/stage1_windows_ip.png" width="220"></a>
  <a href="artifacts/screenshots/stage1_verify_ping.png"><img src="artifacts/screenshots/stage1_verify_ping.png" width="220"></a>
  <a href="artifacts/screenshots/stage1_vm_network_editor.png"><img src="artifacts/screenshots/stage1_vm_network_editor.png" width="220"></a>
</p>

---
