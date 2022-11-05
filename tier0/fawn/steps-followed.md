FAWN - machine - Tier 0

## Steps followed
1. Connect to the VPN
2. Spawn the machine
3. Ping to check the connectivity of to the machine
	`ping {ip-address}`
4. Triggered an nmap scan with service detection flag. Found ftp service to be runnign in the machine. `nmap -sV {ip-address}`
5. Found the below details from the nmap scan
   1. Version of FTP to be `vsftpd 3.0.3`
   2. OS: `unix`
6. Used the FTP command to connect to the FTP service: `ftp {ip-address}`
   1. username: `anonymous`
7. Once logged in, used the `ls -a` command to list all the files and found the flag.txt file.
8. Ran the `less flag.txt` command and copied the flag. Alternatively we can use `get flag.txt` command to download the flag.txt to the local machine and then view it.
9. Flag: **035db21c881520061c53e0536e44f815**

## Tools/commands used
1. ping 
2. nmap
3. ftp
4. ls
5. get flag.txt & less flag.txt (in the FTP connection)

## Interesting note
+ FTP services also come with a GUI, similar to Windows OS Programs, enabling easier navigation for beginners. An example of a well-known GUI-oriented FTP Service is [FileZilla](https://filezilla-project.org/).
+ Secure FTP
  + **SSL/TLS (FTPS)** - Adds an additional security layer of TLS over the legacy FTP protocol. In terms of transfer speeds, this is much faster than SFTP (due to the high resource overhead).
  + **SSH-tunneling (SFTP)** - Build on SSHv2 to add capability to transfer files securely. It terms of support, SFTP is more widely supported as FTPs is build on the FTP protocol that is being phased out gradually.

## Summary
This is an introductory machine and helps us understand the very basics of connectivity testing, service enumeration, basic linux knowledge, ftp service. 