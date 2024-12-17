# Password-Hacking-Hash-Injection-Attack---Proof-of-Concept
A hash injection attack involves injecting a hash value (such as NTLM or LM hashes in Windows environments) directly into an authentication process without needing to crack it. This technique exploits the trust a system places in valid hash values, allowing attackers to impersonate legitimate users.

Extracting Credentials Using fgdump
First, by executing fgdump on the target (after downloading and extracting it on the target), a file is generated in the same location as the fgdump.exe file. This file contains the results of the credential extraction process.

![image](https://github.com/user-attachments/assets/a23d17a5-a486-4487-a989-7fec7d54d460)
![image](https://github.com/user-attachments/assets/88d61583-945d-4a5e-95b6-55cadcc8813b)

 
The fgdump output is copied and made available on our Linux system (e.g., testhash-win.txt in this case), where it will be used for remote access.
 
 
If the target user does not have an LM hash, a dummy (empty) hash is required. This hash can easily be obtained from any hash converter and is then assigned to the user.
 
Next, both the LM and NT hashes are copied, and a new variable (HASH) is created in another terminal for further use.
 
In this step, the pth-winexe command is used to execute commands remotely on the target system.

 
Once the pth-winexe command is successfully executed, remote access to the target system should be granted. Once inside, we have full control over the system, including the ability to:
•	Modify, read, and delete files.
•	Change system configurations and settings.
•	Install or remove software.
•	Manage user accounts and permissions.
•	Execute further commands or scripts.
•	Transfer files between the target and our system.
•	Collect system information, such as running processes, network settings, and hardware configurations.
•	Access system logs and perform reconnaissance.
Since we also have administrator rights, we can perform high-level actions like elevating privileges, disabling security features (such as antivirus or firewalls), and making persistent changes to maintain access to the target system.
