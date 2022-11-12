# dancing - machine - Tier 0

## Steps followed
1. Connect to the VPN
2. Spawn the machine
3. Ping to check the connectivity of to the machine
	`ping {ip-address}`
4. Triggered an nmap scan with service detection flag. Found smb service to be runnign in the machine. `nmap -sV {ip-address}`
5. Used the `smbclient` tool for further analysis.
6. Tried listing the **shares** for the give `ip-address` using `smbclient -L {ip-address}` 
   1. There were four shares returned
      1. `ADMIN$`
      2. `C$`
      3. `IPC$`
      4. `WorkShares`
7. Checked if I was able to connect to any of these shares using `smbclient \\\\{ip-address}\\{share-name}`
   1. Was able to successfully connect to `WorkShares` share
8. The smb service supports the general `ls`, `cd` and `more` commands. Used these commands to checkout the dirs present and found a file named `flag.txt` and got the flag.

## Tools/commands used
1. ping 
2. nmap
3. smbclient

## Interesting note
### smb protocol
This communication protocol provides shared access to files, printers, and serial ports between endpoints on a network. We mostly see SMB services running on Windows machines.

During scanning, we will typically see port **445 TCP open** on the target, reserved for the SMB protocol. Usually, SMB runs at the Application or Presentation layers of the OSI model, pictured below. Due to this, it relies on lower-level protocols for transport. The Transport layer protocol that Microsoft SMB Protocol is most often used with is NetBIOS over TCP/IP (NBT). This is why, during scans, we will most likely see both protocols with open ports running on the target.

### Variants of smb protocol
+ SMBv1 - Released by IBM for file sharing in DOS. - 1984
+ CIFS - Came in Windows 95 - 1996
+ SMBv2 - Windows Vista - 2006
+ SMBv2.1 - Windows 7 - Performance improvements
+ SMBv3 - Windows 8 - Started to support end-to-end encryption
+ SMBv3.1.1 - Windows 10 - 2015 - Additional security elements.

### Incidents where the vulnerabilities were exploited
In 2017, there was a vulnerability that was found in SMBv1 protocol. This allowed the attacker to execute code without the user noticing it. Exploiting one device can enable the attacker to gain access to the while network and every device connected to it.

This exploit was called the EternalBlue. This exploit was used in the WannaCry ransomware attack.


## Summary
This is an introductory machine and helps us understand the very basics of connectivity testing, service enumeration, basic linux knowledge, smb service. 

## Resources
+ For more details on how to test the SMB protocol, please refer - https://book.hacktricks.xyz/network-services-pentesting/pentesting-smb.