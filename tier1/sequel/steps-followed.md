# appointment - machine - Tier 1

## Steps followed
1. Connect to the VPN
2. Spawn the machine
3. Ping to check the connectivity of to the machine
	`ping {ip-address}`
4. Service enumeration using nmap: `nmap -sV ${ip-address}`
   1. Found **port 3306 open** and running **mysql?**
5. Connected to the mysql db using `mysql -h {ip-address} -u root`
   1. Seems like it was running mariadb.
6. Listed all the dbs using `show databases;`
   1. htb database seems interesting.
7. Used the htb database using `use htb;`
8. Listed all the tables in the htb database using `show tables;`
   1. config
   2. users
9. Printed all the contents of both the tables and found the flag to be in config table.
   1.  Used the command - `select * from {tablename};`


## Tools/commands used
1. ping 
2. nmap
3. mysql


## Interesting note
TODO: FILL THIS

## Summary
This is an introductory machine and helps us understand the very basics of db commands and connecting to a remote db. Also points us to the importance of updating the default creds.

## Resources
+ TODO: FILL THIS