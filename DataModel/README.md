# Internet Access for Linux-Clients in my virtual Lab
I want to bulid a Internet Service for my 4 Linxus Host which gets the IP-Address from DHCP.
* DHCP-Server : running on the Routers R-1 and R-4.
* Internet Access via NAT which is configured R-2, it uses PAT to the MGMT-Interface.
* OSPF on all Routers 
* Every Linux Workstation should be able to ping google's DNS

## Steps:

### Prepair Infrastructur
* configure loopback interfaces on the routers
* run ospf, originate default route
* create NAT-Policy

### Service for the Clients
* configure vlans for the linux hosts connected on the switches
* Prepair DHCP-Pools (1 Pool per Host)
* Configure Router Interfaces matching that pools
* distribute Routes 

### Found some issues and try to solve with nornir
