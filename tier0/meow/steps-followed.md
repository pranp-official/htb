# MEOW machine - Tier 0

## Steps followed
1. Connect to the VPN
2. Spawn the machine
3. Ping to check the connectivity of to the machine
	`ping {ip-address}`
4. Triggered an nmap scan with service detection flag. Found telnet service to be runnign in the machine.
	`nmap -sV {ip-address}`
5. Read a bit about telnet - "Telnet is a network protocol that gives users a UNsecure way to access a computer over a network."
6. Connected to the system using the telnet tool
	`telnet {ip-address}`
7. Tried a few common login usernames like admin, administrator, root. The root username worked and was able to login to the machine successfully.
8. Listed all the file available on the machine using the ls command.
	`ls`
9. Found the flag file and did a `cat {file-name}` to show the flag.

## Summary
This machine is an introductory machine and helps us understand the very basics of connectivity testing, service enumeration, basic linux knowledge, telnet service. 
