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

---

## Client-Based VPN for remote access

![Client_based_VPN](Images/Client_based_VPN.png)

![remote_user_creation](Images/remote_user_creation.png)

![remoteaccess_connection](Images/remoteaccess_connection.png)

![remoteaccess_connection_info](Images/remoteaccess_connection_info.png)

![server_address_for_remoteaccess](Images/server_address_for_remoteaccess.png)

![Remoteaccess_properties](Images/Remoteaccess_properties.png)

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

---












































