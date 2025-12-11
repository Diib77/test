# Blue - Writeup (Easy)

**Platform:** HackTheBox | **OS:** Windows

## 1. Reconnaissance
I started with a standard Nmap scan:
`nmap -sC -sV -oA nmap/initial 10.10.10.27`

We see port **445** is open. This looks like EternalBlue (MS17-010).

## 2. Exploitation
Using Metasploit, I searched for the exploit:
`search eternalblue`

I selected `exploit/windows/smb/ms17_010_eternalblue`.
> **Note:** Make sure to set LHOST to your tun0 interface!

## 3. Privilege Escalation
The exploit dropped me directly into a `NT AUTHORITY\SYSTEM` shell. No manual privesc needed!

**Root Flag:** `b4ea...`