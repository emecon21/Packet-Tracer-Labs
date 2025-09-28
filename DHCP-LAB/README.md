# DHCP Configuration Lab

This lab shows how to configure a Cisco Router as a **DHCP server** to automatically assign IP addresses to network devices.

## Steps I Followed
1. Network Topology Setup
   - Added one router, two switches and multiple PCs in Packet Tracer
   - Connected devices using copper straight-through cables
     
     
2. Router Configuration
   - Entered enable and configure terminal mode
   - Assigned IP addresses to the router interfaces (g0/0: 192.168.1.1/24) (g0/1: 172.16.2.1/24)
   - Enabled the interfaces with "no shutdown"
   

3. DHCP Configuration
   - Created DHCP pools:
   (ip dhcp pool LAN1
   network 192.168.1.0 255.255.255.0
   default-router 192.168.1.1
   dns-server 8.8.8.8)

        (ip dhcp pool LAN2
   network 172.16.2.0 255.255.255.0
   default-router 172.16.2.1
   dns-server 8.8.8.8)
   - Excluded the router's own IP from the pool:
   (ip dhcp excluded-address 192.168.1.1) 
   (ip dhcp excluded-address 172.16.2.1)

4. Testing
   - Set each PC's IP configuration to DHCP
   - Verified that the PCs automatically recieved IP addresses from the router using "ipconfig /all" in the PC command prompt

5. Verification
   - Pinged from one PC to another to ensure connectivity
   - Checked that each PC got a valid IP in the correct range
  
## What I Learned
   - How DHCP automates IP addressing
   - Basic Cisco IOS commands for DHCP


You can follow the steps above or explore the configurations already in place.
