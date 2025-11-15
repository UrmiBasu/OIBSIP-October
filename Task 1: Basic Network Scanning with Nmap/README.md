**Nmap Scan Results**

This document summarizes and explains the results of an Nmap service scan of host \*\*44.228.249.3\*\* (an AWS EC2 instance).

**Scan Command**

nmap \-sV \-oN nmap\_scan\_results.txt 44.228.249.3

\-sV: Enables version detection to identify service versions running on open ports.

\-oN: Outputs the results in normal format to a file.

**Summary of Findings**  
Nmap discovered one open TCP port on the target system:

Port       State    Service  Version         

80/tcp    open    http        nginx 1.19.0

All the other 999 TCP ports were reported as filtered, which means the scanner got no response; this is usually caused by a firewall or security group blocking access.

**Interpretation**

Host is Reachable  
This host responded to probes, which indicates it is online with a latency of approximately 0.28 seconds.

Open Port Identified (HTTP on Port 80\)

Port 80 is open and is running an nginx 1.19.0 web server.

This indicates the system is serving HTTP traffic.

If this server hosts a website or API, it's accessible to standard web traffic unless restricted by additional routing or firewall rules.

**Filtered Ports**  
Nmap reported 999 filtered ports, which means:

The server may be behind a firewall or AWS security group.

These ports did not respond at all (not even with a rejection), which is typical for packets that have been dropped/filtered.  
Security Considerations  
nginx 1.19.0 is an older release; if this system is in production, you should review update requirements or security patches.  
The presence of only one open port indicates tight perimeter restrictions, which is a good practice.  
Assess the Firewall/AWS Security Group Configuration for the need to expose only required ports.   
Full Raw Output Host is up (0.28s latency). Not shown: 999 filtered tcp ports (no-response) PORT   STATE SERVICE VERSION 80/tcp open  http    nginx 1.19.0  
