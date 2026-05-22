# Enterprise Network Project - Security


## Project Overview 
A secure multi-site network infrastructure built using two FortiGate firewalls, site-to-site VPN connections, Client-Based VPN connection, and an AWS Cloud Tunnel integration. This setup forwards all network, server, and VPN logs into a centralized Splunk SIEM platform, providing full visibility and successful detection of active cyber attacks simulated through a Kali Linux attacker VM.

---

## Diagram
![diagram](Images/diagram.png)

---

## Addressing Scheme
![addressing](Images/addressing.png)

---

## Site-to-site VPN Implementation

Site 1 to Site 2:

![site1_to_site2_tunnel](Images/site1_to_site2_tunnel.png)
![status_tosite2](Images/status_tosite2.png)

#

Site 2 to Site 1:

![site2_to_site1_vpn](Images/site2_to_site1_vpn.png)
![status_tosite1](Images/status_tosite1.png)

















