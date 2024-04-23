# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/7bece3ab-b5a2-4af3-816f-6391d9b1e58f)

## Invoke msfconsole:

## OUTPUT:
![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/bf56d726-935f-44b8-bb66-0c958ae61479)


## OUTPUT:
![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/4f7ca842-728f-48d8-8eb0-283da6385ab1)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## output:
![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/b4bb7c82-f8d7-4d54-a494-a66a32704d39)

### Step4: 

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT::

![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/06867a61-6689-4c03-b87d-1d0860dfe720)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## output:
![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/7dd822d1-1547-488e-bcd6-f862eedfa186)


![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/37831252-ecb1-4920-8c3b-62f4462e62ca)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/d568338f-d5ed-424e-b097-4e3ae85c9127)


The info command provides information regarding a module or platform
## OUTPUT:
![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/b12e262c-5a39-4800-a269-e64ae087fe1c)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/489f2691-ae86-46fb-8572-8662694f6678)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/728d950e-45c5-4c40-9263-008f9a1ccb4d)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/1b3480b9-7768-4771-b4c5-d2a933112764)

Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/000c5538-3bfa-4144-a4bb-fc90d4ba1271)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/12116ec2-20c7-4682-acce-dc7a8e008685)


 set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

 ![image](https://github.com/skiruthika648/Metasploit-for-reconnaissance/assets/128348968/51a9fbf5-0646-4f24-9b82-f0cbd582c1c4)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
