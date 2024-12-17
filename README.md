# Password-Hacking-Hash-Injection-Attack - Proof-of-Concept
A hash injection attack involves injecting a hash value (such as NTLM or LM hashes in Windows environments) directly into an authentication process without needing to crack it. This technique exploits the trust a system places in valid hash values, allowing attackers to impersonate legitimate users.

Extracting Credentials Using fgdump: First, by executing fgdump on the target (after downloading and extracting it on the target), a file is generated in the same location as the fgdump.exe file. This file contains the results of the credential extraction process.

![image](https://github.com/user-attachments/assets/a23d17a5-a486-4487-a989-7fec7d54d460)
![image](https://github.com/user-attachments/assets/88d61583-945d-4a5e-95b6-55cadcc8813b)

The fgdump output is copied and made available on our Linux system (e.g., testhash-win.txt in this case), where it will be used for remote access.

![image](https://github.com/user-attachments/assets/15e541b7-8dc5-4b50-8cef-acf11d47c760)
![image](https://github.com/user-attachments/assets/58e92cef-2eaa-4a7f-a467-db1e37332093)
 
If the target user does not have an LM hash, a dummy (empty) hash is required. This hash can easily be obtained from any hash converter and is then assigned to the user.

![image](https://github.com/user-attachments/assets/4acb1537-c787-41c6-a146-7a9be24c0a54)

Next, both the LM and NT hashes are copied, and a new variable (HASH) is created in another terminal for further use.

![image](https://github.com/user-attachments/assets/d75fa0e2-e221-4435-8b3e-391ee05f21ca)
 
In this step, the pth-winexe command is used to execute commands remotely on the target system.

![image](https://github.com/user-attachments/assets/ed2f0be2-dcc3-44f7-953e-0e500c79e9c2)

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
