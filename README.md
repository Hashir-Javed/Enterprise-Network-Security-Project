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

Site1 tunnel up:
![status_tosite2](Images/status_tosite2.png)

#

Site 2 to Site 1:

![site2_to_site1_vpn](Images/site2_to_site1_vpn.png)

Site2 tunnel up:
![status_tosite1](Images/status_tosite1.png)

---

## Client-Based VPN for remote access

![Client_based_VPN](Images/Client_based_VPN.png)

User credentials created for ClientVPN Connection:
![remote_user_creation](Images/remote_user_creation.png)

![remoteaccess_connection](Images/remoteaccess_connection.png)

Correct connection properties displayed:
![remoteaccess_connection_info](Images/remoteaccess_connection_info.png)

![server_address_for_remoteaccess](Images/server_address_for_remoteaccess.png)
#
Remote access VPN type in use is L2TP with IPSec due to its enhanced security. L2TP creates a secure tunnel for data transfer, while IPSec encrypts the data within that tunnel, ensuring that the data remains confidential and protected from unauthorized access:
![Remoteaccess_properties](Images/Remoteaccess_properties.png)

Client VPN connection active
![remote_connection_up](Images/remote_connection_up.png)

---

## Apache Web Server and SSH Server set up for remote accessible connections

![Apache_web_server_running](Images/Apache_web_server_running.png)
![SSH_Server_running](Images/SSH_Server_running.png)

---

## Connectivity through VPN tunnel to servers from remote user established

Ping test:

![connectivity_through_site_to_site_vpn](Images/connectivity_through_site_to_site_vpn.png)

#

Apache Web Server connection test:

![apache_web_server_accessible](Images/apache_web_server_accessible.png)

#

SSH Server connection test:

![SSH_Server_accessible](Images/SSH_Server_accessible.png)

---

### Logging and Splunk setup to collect logs from required core devices

FortiGate1:

![FORTIGATE1_log_settings](Images/FORTIGATE1_log_settings.png)
![FORTIGATE1_CLI_syslog_show](Images/FORTIGATE1_CLI_syslog_show.png)

#

FortiGate2:

![FORTIGATE2_log_settings](Images/FORTIGATE2_log_settings.png)
![FORTIGATE2_CLI_syslog_show](Images/FORTIGATE2_CLI_syslog_show.png)

#

Apache Web Server:

![Apache_web_server_log_settings](Images/Apache_web_server_log_settings.png)

#

SSH Server:

![SSH_server_log_settings](Images/SSH_server_log_settings.png)

#

Splunk Server UDP listening ports setup:

![UDP_data_inputs](Images/UDP_data_inputs.png)

---


### Attack Simulation

Before simulating the attacks, a DOS policy is configured to block unwanted anomalies:

![Dos_policy](Images/Dos_policy.png)
![Dos_policy_cont](Images/Dos_policy_cont.png)

UDP Flood Attack:

![Udp_flood_attack](Images/Udp_flood_attack.png)
![Udp_flood_anomaly](Images/Udp_flood_anomaly.png)

UDP Flood Attack successfully logged:

![udp_flood_detection](Images/udp_flood_detection.png)

#

ICMP Echo Flood Attack:

![Icmp_flood_attack](Images/Icmp_flood_attack.png)
![Icmp_flood_anomaly](Images/Icmp_flood_anomaly.png)

ICMP Echo Flood Attack successfully logged:

![icmp_detect](Images/icmp_flood_detection.png)


#

NMAP Scan Attack:

![NMAP](Images/NMAP.png)

NMAP Scan Attack successfully logged:

![NMAP_Detection](Images/NMAP_Detection.png)

---

## All Firewall and Server logs collected in Splunk

FortiGate1: 

![FORTIGATE1_LOGS](Images/FORTIGATE1_LOGS.png)

#

FortiGate2:

![FORTIGATE2_LOGS](Images/FORTIGATE2_LOGS.png)

#

Apache Web Server:

![APACHE_web_server_logs](Images/APACHE_web_server_logs.png)

#

SSH Server:

![SSH_Server_logs](Images/SSH_Server_logs.png)

---


## AWS Integration

When setting up a VPN connection to AWS, two tunnels are automatically provisioned by AWS to maximize availability and eliminate single points of failure. With this in mind, it is best practice to take advantage of this design and configure both separate tunnels on the FortiGate firewall. Although, it is possible to bring up only a single tunnel and still maintain connectivity between both environments, we chose to utilize the dual-tunnel capability to ensure high availability and network resiliency in our enterprise environment

---

Tunnel 1:

![1st_AWS_vpn_tunnel](Images/1st_AWS_vpn_tunnel.png)

Tunnel 2:

![2nd_AWS_vpn_tunnel](Images/2nd_AWS_vpn_tunnel.png)

Dual tunnel interfaces active under WAN1:
![AWS_tunnel_interfaces](Images/AWS_tunnel_interfaces.png)

Static Routes set for each tunnel:
![static_routes](Images/static_routes.png)

Firewall Policies in place:
![AWS_Firewall_policies](Images/AWS_Firewall_policies.png)

Both tunnels are successfully established and actively running:
[AWS_tunnel_connections](Images/AWS_tunnel_connections.png)
![AWS_tunnel_connections_up](Images/AWS_tunnel_connections_up.png)

The AWS console verifies that both VPN connection tunnels are successfully established and functioning as required:
![AWS_tunnel_status_up_from_console](Images/AWS_tunnel_status_up_from_console.png)

---

## Dashboard Creation


![Dashboard](Dashboard.pdf)

## FortiGate1 Sanitized configuration file

![FG1 Config](FORTIGATE1_Sanitized.conf)

## FortiGate2 Sanitized configuration file

![FG2 Config](FORTIGATE2_Sanitized.conf)


















































