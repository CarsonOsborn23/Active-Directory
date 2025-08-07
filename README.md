#  Active Directory

## Objective
The goal of this project was to build a controlled lab environment to simulate cyber attacks and analyze them using a Security Information and Event Management system. This hands-on experience was designed to improve practical cybersecurity skills, including threat detection, log analysis, and Active Directory administration.

## Skills Developed
- Proficient use of Security Information and Event Management tools for log ingestion and threat detection
- Strong understanding of Active Directory, DNS, and Group Policy management
- Generated attack telemetry to identify common attack patterns
- Deepened knowledge of network traffic, protocols, and vulnerabilities

##  Tools Used
- Windows Server (Active Directory Domain Services, DNS, Group Policy)
- Splunk was used for real-time monitoring of security and threat detection while gathering my virtual machines' data
- PowerShell and scripting utilities for configuration
- AtomicRedTeam was used to simulate and test attacks on my target machine with the help of Splunk
- Kali Linux was used as the attacking machine
- Hydra was used to brute force an Active Directory user I created

## Project Workflow
<img width="1225" height="544" alt="virtual machines" src="https://github.com/user-attachments/assets/8ea35fd4-be56-4c6a-8e9c-27df4cfcab05" />
I installed the Virtual Machines to my Virtual Box and added a Windows Server, Kali, Windows 8 target-PC and Splunk
<img width="1212" height="846" alt="set up splunk server" src="https://github.com/user-attachments/assets/a98bef0b-02e4-43c1-b204-200be6d5f347" />
I Installed Splunk and created my admin account in it
<img width="1013" height="813" alt="Installed and Configured Splunk and Sysmon on the target-Pc" src="https://github.com/user-attachments/assets/bbee8d80-c380-4b8d-8d50-3eafb4ebd596" />
I installed Splunk and Sysmon on the target-PC then configured them
<img width="1017" height="804" alt="Installed and Configured Splunk and Sysmon on the Windows-Server also" src="https://github.com/user-attachments/assets/a90ae00e-41ba-4edd-92f5-4f831bd462a1" />
I then installed Splunk and Sysmon for the Windows Server then configured them
<img width="1013" height="827" alt="Set up Active Directory and Made the server a domain controller" src="https://github.com/user-attachments/assets/bbc074ec-cc37-47ed-ab5a-14a0469a8e9d" />
I set up Active Directory on the Windows Server and made it a Domain Controller
<img width="1828" height="817" alt="I created a new user in active directory and then joined the computer to the domain i created using the created user" src="https://github.com/user-attachments/assets/1eb04d52-8766-4aed-bf13-89ef3a51b593" />
I created two new users in Active Directory and then i joined the target-PC to the Windows Servers Domain
<img width="786" height="655" alt="I successfully brute forced tsmiths user account" src="https://github.com/user-attachments/assets/283b2fbd-b876-4a2b-83eb-79637a7ae514" />
I then successfully brute forced tsmiths user account using the password cracking tool Hydra
<img width="1003" height="787" alt="Screenshot 2025-08-03 185924" src="https://github.com/user-attachments/assets/215c8263-d345-4902-8dea-8e6d64f7d969" />
I then went into Splunk and found the 20 failed logons which would be a red flag in the real world
<img width="992" height="810" alt="Screenshot 2025-08-03 190036" src="https://github.com/user-attachments/assets/0a219b74-571c-4fe6-b243-18cbc11a5562" />
I then switched the event code to 4624 to see if the logon was successful and it did successfully logon to tsmiths user account
<img width="1002" height="801" alt="Screenshot 2025-08-03 190206" src="https://github.com/user-attachments/assets/c89fa31e-ffa3-41d0-bcd4-c53cdee09ddf" />
After acknowledging that an account logon was successful I checked the network information and it was the attacker machine hosted on kali with the static ip I created for it
<img width="1013" height="810" alt="Downloaded atomic red team on the target machine" src="https://github.com/user-attachments/assets/f2522c21-c828-4d5a-a6dd-1dc322f6b14c" />
I then downloaded atomicredteam on the target machine to test the security of my target machine with the help of Splunk
<img width="995" height="837" alt="Invoking an atomic red team test on create account under local account T136 001" src="https://github.com/user-attachments/assets/98edf601-c4ea-4ed0-96da-b82b82421b37" />
Once atomicredteam was downloaded I invoked my first test under T136.001 which is creating a new user account
<img width="1003" height="855" alt="Got no hits on Splunk for NewLocalUser which means its blind to this activity and theyd go undetected under a new local user" src="https://github.com/user-attachments/assets/85d12b1e-edfd-4697-b56f-687a32805c0d" />
After testing this I inspected the Splunk index and it did not pick up a hit for NewLocalUser and that means an attacker could create a new local user and it will go undetected which means this is a security threat
<img width="965" height="837" alt="Innvoked atomic red team test on T1059 001 (powershell) and got a hit" src="https://github.com/user-attachments/assets/76d59e1c-51d2-4b18-b8c6-73751ba3d60d" />
I then used atomicredteam to invoke a final test on T1059.001 which is powershell and we did get a hit so this means it will be detected if an attacker tries this method










## Network Diagram 
<img width="532" height="675" alt="Active Directory Diagram drawio" src="https://github.com/user-attachments/assets/38992138-c1a9-4e8a-98a9-0b26053dc859" />



