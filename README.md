# Basic-Routing-Technology

connected the console cable from the PC to the router with the blue cable and added the Ethernet cable which is the green one to the G0/0 on the router. 

 

To enter the configuration mode, I double clicked on the PC  > desktop > terminal. 

To change the hostname: 

Enable 

Configure terminal 

Hostname RoutingTech 

To disable the DNS lookup: 

No ip domain-lookup 

Assign secret password: 

(In configure terminal) Enable secret EnP@$$ 

Assign consol password + enable login : 

(In configure terminal) line console 0 

Password  ConP@$$ 

Login 

>> to check I must exit then in show mode (#) execute show running-config 

~ we always login to the console then we use the privilege mode~ 

Assign VTY password + enable login : 

(In configure terminal) line vty 0 4 

Password SSHP@$$ 

Login 

>> to check I must exit then in show mode (#) execute show running-config 

To encrypt the plain text passwords: 

(In configure terminal) service password-encryption 

To create a banner: 

(In configure terminal) banner motd #Unauthorised access is not permitted# 

Giving a router interface an IP address + changing the status from down to up: 

In show mode (#) show ip interface brief 

(In configure terminal)  Interface GigabitEthernet0/0/0  

Description Link to PC 

Ip address 192.168.1.1 255.255.255.0 

No shutdown  

 

To save running configuration to startup configuration: 

In show mode (#) show running-config 

Show startup-config (to see the startup) 

copy running-config startup-config 



# To configure a static route on routers >> 

(Configuration mode) Ip route {network address} {subnet mask} {next hop IP address or exit interface (look for the last exit hop)} 

For example, >> clicked on R1 and destination which I want to connect to is 192.168.20.0/24 and the router after that PC has 172.16.1.2 Ip address to connect to R1. >> ip route 192.168.20.0 255.255.255.0 172.16.1.2 

To check the ip route >>  

(in show mode) show ip route  

OR  

show ip route | begin Gateway 


 

If there is an internet there where we didn’t know if there is other router so we will use G0/0/0 then the entry after the internet to the last router. 

172.16.0.0	255.255.255.0	G0/0/0		18.72.55.88 

Loopback >> 

There is no limit on the number of loopback interfaces you can create, and it doesn’t have internal VLAN IDs or MAC addresses. 

The command to configure loopback on switch and router is >> configure terminal, interface loopback 1, ip address 192.168.1.1 255.255.255.0, exit  

Cisco Discovery protocol >> cisco devices share info with their neighbours. Layer 2 protocol which is media and network independent. 

Show cdp neighbors 

Show cdp neighbors detail 

 

Line vty is used for remote access to the cisco device through SSH, Telnet > and the numbers are vty 0 15 means vty line 0 through 15 which giving 16 virtual terminal line 

Line console is used when we physically connected to the device with a console cable  

 

Adding minimum password length for security >> security password min-length 8 

Ip domain-name routing.tech to find the domain name of the routing tech. 
