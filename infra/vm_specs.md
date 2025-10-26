# VM Specs — Host-only Attack+Detect Lab

**Network:** Host-only (VMnet1) — `172.16.94.0/24`

| VM Name | Role            | OS / Version        | RAM  | vCPU | Disk  | IP Address       | Snapshots                             |
|---------|-----------------|---------------------|------|------|-------|------------------|----------------------------------------|
| Kali    | Attacker        | Kali Rolling 2025.x | 4 GB | 2    | 40 GB | 172.16.94.128    | `kali_clean`                           |
| Windows | Target (Victim) | Windows 10 Pro x64  | 8 GB | 2–4  | 60 GB | 172.16.94.133    | `win10_x64_clean`, `win10_preexploit` |
| Ubuntu  | Log / Detection | Ubuntu 22.04 LTS    | 6–8G | 2    | 40 GB | 172.16.94.131    | `ubuntu_clean`                         |

---

### Notes
- **Host-only** = isolated lab (no gateway).  
- Add **NAT only when needed** for updates; then disconnect it for testing.  
- Always **snapshot before scanning or exploiting**.
