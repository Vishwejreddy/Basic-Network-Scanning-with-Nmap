
NMAP SCAN RESULTS

Target IP:
192.168.29.176

Scan Date:
30/06/2026

1. Basic Scan

Command:

nmap 192.168.29.176

Result:

PORT     STATE SERVICE
135/tcp  open  msrpc
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
7070/tcp open  ssl/realserver?
8090/tcp open  tcpwrapped


2. Service Version Scan


Command:

nmap -sV 192.168.29.176

Result:

PORT     STATE SERVICE        VERSION

135/tcp  open  msrpc          Microsoft Windows RPC
139/tcp  open  netbios-ssn    Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds?
7070/tcp open  ssl/realserver?
8090/tcp open  tcpwrapped


3. Operating System Detection


Command:

nmap -O 192.168.29.176

Result:

Running:
Microsoft Windows 11

OS Details:
Microsoft Windows 11 24H2 - 25H2

Device Type:
General Purpose

Network Distance:
0 hops

Open Port Analysis


Port 135 (MSRPC)

Purpose:
Microsoft Remote Procedure Call service used by Windows for communication between applications and system services.

Security Risk:
If exposed to untrusted networks, attackers may exploit RPC vulnerabilities or gather information about the system.



Port 139 (NetBIOS-SSN)

Purpose:
Provides NetBIOS Session Service for Windows file and printer sharing.

Security Risk:
Can reveal shared resources and user information. It should not be exposed to public networks.


Port 445 (Microsoft-DS)

Purpose:
Used by SMB (Server Message Block) for Windows file and printer sharing.

Security Risk:
Frequently targeted by malware and ransomware such as WannaCry. SMB should be protected with firewalls and security updates.



Port 7070 (SSL/RealServer)

Purpose:
Used by an application or service running over SSL/TLS.

Security Risk:
Unknown or unnecessary services should be reviewed. Outdated SSL configurations may expose vulnerabilities.


Port 8090 (TCPWrapped)

Purpose:
Indicates that a TCP service is running but access is restricted or filtered.

Security Risk:
Although the service is protected, administrators should verify whether it is required and properly secured.


Summary


Total Open Ports: 5

Detected Services:

Microsoft Windows RPC
NetBIOS Session Service
Microsoft-DS (SMB)
SSL/RealServer
TCPWrapped

Detected Operating System:

Microsoft Windows 11 (24H2 - 25H2)

Recommendations:

1. Close any unused open ports.
2. Keep Windows and installed applications updated with the latest security patches.
3. Restrict SMB (Port 445) and NetBIOS (Port 139) access using Windows Firewall.
4. Disable unnecessary services that are not in use.
5. Use strong passwords and enable Windows Defender Firewall.
6. Monitor system and network logs regularly for suspicious activity.
7. Perform periodic vulnerability scans using Nmap and other security tools.

End of Report
