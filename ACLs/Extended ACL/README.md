## Named Extended ACL Configuration

This lab shows how I configured a Named Extended Access Control List (ACL) on a network topology.

The configuration was to deny HTTP traffic from devices on NETWORK C to the Server on NETWORK A, while allowing other ip traffic and other networks.

## Steps Followed
1. Network Topology Setup
    - One router
    - Three switches
    - Four PCs (Two each in Networks B&C)
    - One server (Network A)


2. IP Addressing Plan
   
    | Device | Interface | IP Address | Network |
    |---------|------------|-------------|----------|
    | PC1 | NIC | 192.168.20.6 | 192.168.20.0/24 |
    | PC2 | NIC | 192.168.20.7 | 192.168.20.0/24 |
    | PC3 | NIC | 192.168.30.8 | 192.168.30.0/24 |
    | PC2 | NIC | 192.168.30.9 | 192.168.30.0/24 |
    | R1 | G0/0 | 192.168.10.1 | 192.168.10.0/24 |
    | R1 | G0/1 | 192.168.20.1 | 192.168.20.0/24 |
    | R1 | G0/2 | 192.168.30.1 | 192.168.30.0/24 |
    | Server 1 | NIC | 192.168.10.5 | 192.168.10.0/24 |


3. Router Configurations

   On R1
  
   I assigned IP addresses to router interfaces after PC configurations, in the global configuration mode.

    - int g0/0
    - ip address 192.168.10.1 255.255.255.0
    - no shutdown
    - exit
    


    - int g0/1
    - ip address 192.168.20.1 255.255.255.0
    - no shutdown
    - exit



    - int g0/2
    - ip address 192.168.30.1 255.255.255.0
    - no shutdown
    - exit
      

  I then created a Named Extended ACL to deny HTTP from Network C to the Server network while permitting other network and ip traffic;
    
    - ip access-list extended BLOCK_HTTP
    - deny tcp 192.168.30.0 0.0.0.255 192.168.10.0 0.0.0.255 eq 80
    - permit ip any any
    - exit

  Applied ACLs to Router interface;

    - int g0/2
    - ip access-group BLOCK_HTTP in
    - exit 

  After creating and applying the ACL, I saved the configuration settings;

    - copy running-config startup-config

4. Testing and Verification

    - used "show run" to display running configurations on the router
    - attempted an http request to the server before applying ACL
    - confirmed ACL imlementation after applying ACL
    - IP traffics from Network B allowed
    - HTTP traffic from Network C denied 
