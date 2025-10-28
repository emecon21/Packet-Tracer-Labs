## Dynamic Routing (OSPF) Configurations
This lab shows how I configured Dynamic Routing with the OSPF protocol between two networks.

The goal was to make both networks communicate automatically, using OSPF, a dynamic routing protocol that chooses the shortest path to destinations.

## Steps Followed
1. Network Topology Setup
   - Two switches
   - Two routers (R1 and R2)
   - Four PCs
   - Connected devices on each network
   - Connected both routers with serial DTE cable

2. IP Addressing Plan

| Device | Interface | IP Address | Network |
|---------|------------|-------------|----------|
| PC1 | NIC | 192.168.30.2 | 192.168.30.0/24 |
| PC2 | NIC | 192.168.30.3 | 192.168.30.0/24 |
| R1 | FA0/0 | 192.168.30.1 | 192.168.30.0/24 |
| R1 | SE0/0/1 | 10.0.0.1 | 10.0.0.0/30 |
| R2 | SE0/0/1 | 10.0.0.2 | 10.0.0.0/30 |
| R2 | FA0/0 | 192.168.40.1 | 192.168.40.0/24 |
| PC3 | NIC | 192.168.40.2 | 192.168.40.0/24 |
| PC4 | NIC | 192.168.40.3 | 192.168.40.0/24 |

3. Router Configurations
   
   On R1
   - Entered global configuration mode, enabled OSPF process ID 1, and advertised connected networks:
   - router ospf 1
   - network 192.168.30.0 0.0.0.255 area 0
   - network 10.0.0.0 0.0.0.3 area 0
   - end

   On R2
   
   I did the same to advertise it's networks:
   - router ospf 1
   - network 192.168.40.0 0.0.0.255 area 0
   - network 10.0.0.0 0.0.0.3 area 0
   - end

5. Testing and Verification
   - Ping from PC1 to PC3 & PC4 (successful)


