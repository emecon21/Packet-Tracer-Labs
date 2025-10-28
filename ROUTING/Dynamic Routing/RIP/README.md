## Dynamic Routing (RIP) Configurations
This lab shows how I configured Dynamic Routing with the RIP protocol between two networks.

The goal was to make both networks communicate automatically, without manually adding static routes.

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
   | PC1 | NIC | 192.168.3.10 | 192.168.3.0/24 |
   | PC2 | NIC | 192.168.3.11 | 192.168.3.0/24 |
   | R1 | FA0/1 | 192.168.3.1 | 192.168.3.0/24 |
   | R1 | FA0/0 | 192.168.1.3 | 192.168.1.0/24 |
   | R2 | FA0/0 | 192.168.1.4 | 192.168.1.0/24 |
   | R2 | FA0/1 | 192.168.5.1 | 192.168.5.0/24 |
   | PC3 | NIC | 192.168.5.5 | 192.168.5.0/24 |
   | PC4 | NIC | 192.168.5.6 | 192.168.5.0/24 |

3. Router Configurations

   On R1
   - Entered global configuration mode, enabled and advertised the networks connected to R1
   - router rip
   - network 192.168.1.0
   - network 192.168.3.0
   - end

   On R2
   
   Did the same on R2 to advertise it's networks;
   - router rip
   - network 192.168.1.0
   - network 192.168.5.0
   - end

4. Testing and Verification
   - Ping from PC1 to PC3 (successful)
   


















