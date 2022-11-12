# redeemer - machine - Tier 0

## Steps followed
1. Connect to the VPN
2. Spawn the machine
3. Ping to check the connectivity of to the machine
	`ping {ip-address}`
4. Nmap port scan to find the open ports
   1. `nmap {ip-address}` - Top 1000 ports, didn't give any results
   2. `nmap --top-ports 2000` {ip-address} - didn't give any results
   3. `nmap -p 1000-999 {ip-address}` - got redis as the open port - 6379
5. Installed redis-cli to interact with the redis db with the command `sudo apt install redis-tools`.
6. Connected to the redis db using `redis-cli -h {ip-address}`
7. Once inside, using `info` command to get info about redis
8. Listing all the databases in redis - `info keyspace` - We see only db0.
9. Selecting the db0 database - `select 0`
10. Listing all the keys in the db - `keys *`
11. Getting the value for **flag** key - `get flag`


## Tools/commands used
1. ping 
2. nmap
3. redis-cli

## Interesting note
Redis is an in-memory key value datastore. In-memory database relies on the primary memory (RAM) instead of storing the data in the disk. As the primary memory is much much faster than the secondary memory, the data retrieval speeds are also high. 

In-memory databases like Redis are typically used to cache data that is frequently requested for quick
retrieval

Any given Redis instance includes a number of databases, each of which can hold many different keys of a variety of data types. Out of the box, a Redis instance supports 16 logical databases (0-15)

## Summary
This is an introductory machine and is focused on redis-cli and helping us understand the very basics of in-memory databases.

## Resources
+ https://book.hacktricks.xyz/network-services-pentesting/6379-pentesting-redis
+ https://www.digitalocean.com/community/cheatsheets/how-to-manage-redis-databases-and-keys
