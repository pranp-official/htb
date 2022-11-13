# appointment - machine - Tier 1

## Steps followed
1. Connect to the VPN
2. Spawn the machine
3. Ping to check the connectivity of to the machine
	`ping {ip-address}`
4. Service enumeration using nmap: `nmap -sV ${ip-address}`
   1. Found **port 80 open** and running **Apache httpd 2.4.38 ((Debian))**
5. To answer one of the questions related to gobuser, installed the tool using `sudo apt install gobuster`
   1. Then used `gobuster --help` to find all the flags supported. As an alternative we can use `tldr gobuster`.
6. Going to the ip in the webbrowser opened a webpage, asking for username and password.
7. Used a very basic sql injection entry in the password to successfully login.
   1. Entry used: `admin' or '1'='1`
   2. Got the flag


## Tools/commands used
1. ping 
2. nmap
3. gobuster


## Interesting note
### What is SQL Injection?
TODO: FILL THIS.


### Protecting against SQL Injection
There are many different techniques of protecting from SQL injections, some of them being 
   + input validation
   + parameterized queries
   + stored procedures
   + implementing a WAF (Web Application Firewall) on the perimeter of the server's network

## Summary
This is an introductory machine and helps us understand the very basics of sql injection.

## Resources
+ https://portswigger.net/web-security/sql-injection
+ https://book.hacktricks.xyz/pentesting-web/sql-injection
+ https://tryhackme.com/room/sqlinjectionlm