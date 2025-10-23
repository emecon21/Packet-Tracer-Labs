## Named Standard ACL Configuration 

This lab demonstrates a Named Standard Access Control List (ACL) configuration in Cisco Packet Tracer.

The goal was to control network traffic by allowing access to two hosts (IT PCs) and denying access to the other two hosts (HR PCs), all from the same network based on their source IP addresses.

## Steps Followed
1. Network Topology Setup
   - One router
   - Two switches
   - Four PCs (IT dept & HR dept)
   - Two servers
  
2. IP Addressing Plan
   
   | Device | Interface | IP Address | Network |
   |---------|------------|-------------|----------|
   | PC1 | NIC | 192.168.10.10 | 192.168.10.0/24 |
   | PC2 | NIC | 192.168.10.20 | 192.168.10.0/24 |
   | PC3 | NIC | 192.168.10.30 | 192.168.10.0/24 |
   | PC4 | NIC | 192.168.10.40 | 192.168.10.0/24 |
   | R1 | G0/1 | 172.20.1.1 | 172.20.1.0/24 |
   | R1 | G0/2 | 192.168.10.1 | 192.168.10.0/24 |
   | Server1 | NIC | 172.20.1.50 | 172.20.1.0/24 |
   | Server2 | NIC | 172.20.1.60 | 172.20.1.0/24 |

4. Router Configurations
   
   On R1
   
   Assigned IP addresses to router interfaces after PC configurations
   - global configuration mode
   - int g0/1
   - ip address 172.20.1.1 255.255.255.0
   - exit

   - int g0/2
   - ip address 192.168.10.1 255.255.255.0
   - exit


   Created a Named Standard ACL to allow IT PCs and block HR PCs access to the Server network
   - ip access-list standard BLOCK_HR
   - permit host 192.168.10.10
   - permit host 192.168.10.20
   - deny any
   - end


   Applied ACLs to Router interfaces
   - int g0/1
   - ip access-group BLOCK_HR out
   - exit
   - wr

5. Testing and Verification
   - tested configurations with "show access-lists" command
   - pinged from the PCs to test connectivity before applying ACL
   - pinged from the PCs to test connectivity after applying ACL
   - IT PCs 1 & 2 allowed
   - HR PCs 3 & 4 denied


   
   

















   

