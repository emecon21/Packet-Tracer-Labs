## Dynamic Routing (EIGRP) Configuration

This project demonstrates **Enhanced Interior Gateway Routing Protocol (EIGRP)** configuration between routers in Cisco Packet Tracer.  
The goal was to enable automatic route sharing between both networks using EIGRP - a fast and efficient dynamic routing protocol.

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
   | PC1 | NIC | 192.168.3.2 | 192.168.3.0/24 |
   | PC2 | NIC | 192.168.3.3 | 192.168.3.0/24 |
   | R1 | fa0/1 | 192.168.3.1 | 192.168.3.0/24 |
   | R1 | se0/0/0 | 10.0.0.1 | 10.0.0.0/30 |
   | R2 | se0/0/0 | 10.0.0.2 | 10.0.0.0/30 |
   | R2 | fa0/1 | 192.168.40.1 | 192.168.40.0/24 |
   | PC3 | NIC | 192.168.40.3 | 192.168.40.0/24 |
   | PC4 | NIC | 192.168.10.4 | 192.168.40.0/24 |

3. Router Configuration

   On R1
   - config t
   - router eigrp 1
   - network 10.0.0.0 0.255.255.255
   - network 192.168.3.0 0.0.0.255
   - end

   On R2
   Created new adjacency by simply inputing the network addresses alone
   - config t
   - router eigrp 1
   - network 10.0.0.0
   - network 192.168.4.0
   - end

4. Testing and Verification
   - Ping from PC1 to PC3 & PC4 (successful)




































