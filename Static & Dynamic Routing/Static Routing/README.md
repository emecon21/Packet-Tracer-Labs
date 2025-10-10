## Static Routing Configuration

This lab demonstrates how I configured **Static Routing** between two routers in Cisco Packet Tracer.  
The goal was to enable communication between two separate networks by manually adding routes on each router.

## Steps Followed
1. Network Topology Setup
   - Two switches
   - Two routers (R1 and R2)
   - Four PCs
   - Connected devices on each network
   - Connected both routers with copper cross-over cable

2. IP Addressing Plan
   
   | Device | Interface | IP Address | Network |
   |---------|------------|-------------|----------|
   | PC1 | NIC | 192.168.2.2 | 192.168.2.0/24 |
   | PC2| NIC | 192.168.2.3 | 192.168.2.0/24 |
   | R1 | FA0/0 | 192.168.2.1 | 192.168.2.0/24 |
   | R1 | FA0/1 | 192.168.4.3 | 192.168.4.0/24 |
   | R2 | FA0/0 | 192.168.6.1 | 192.168.6.0/24 |
   | R2 | FA0/1 | 192.168.4.4 | 192.168.4.0/24 |
   | PC3 | NIC | 192.168.6.5 | 192.168.6.0/24 |
   | PC4 | NIC | 192.168.6.6 | 192.168.6.0/24 |

3. Router Configurations

   On R1
   - Entered global configuration mode and added a static route to reach PC3 & PC4 network through R2
   - ip route 192.168.6.0 255.255.255.0 192.168.4.4
   - end

   On R2
   - Entered global configuration mode and added a static route to reach PC1 & PC2 network through R1
   - ip route 192.168.2.0 255.255.255.0 192.168.4.3
   - end

5. Testing & Verification
   - Pinged successfully from PC2 to PC3





















   
