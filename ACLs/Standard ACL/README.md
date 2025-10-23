## Named Standard ACL Configuration 

This lab shows a Named Standard Access Control List (ACL) configuration in Cisco Packet Tracer.

The goal was to control network traffic by allowing and denying access to specific hosts based on their source IP addresses.

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

3. Router Configurations

