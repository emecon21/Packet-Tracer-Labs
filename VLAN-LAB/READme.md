## Inter-VLAN Routing and Trunking Configurations Lab
This lab is my practice on how to configure VLANs in Cisco Packet Tracer.
The goal is to separate devices into different networks (FINANCE and MARKETING), and then use a router (Router-on-a-Stick) to allow communication between them.


## Steps Followed
1. Network Topology Setup
   - One switch
   - One router
   - Four PCs (2 in FINANCE VLAN, 2 in MARKETING VLAN)
   - Connected PCs to switch access ports
   - Connected switch to router using a straight-through cable on Fa0/5

2. Creating VLANs on the Switch
   
   (VLAN 10 for FINANCE, VLAN 20 for MARKETING)
   - Entered global configuration mode: configure terminal
   - Created VLANs:
     
     vlan 10
     
     name FINANCE
     
     vlan 20
     
     name MARKETING

3. Assigning VLANs to Interfaces
   
   - interface fa0/1
   
     switchport mode access
   
     switchport access vlan 20

   - interface fa0/2
   
     switchport mode access
   
     switchport access vlan 20

   - interface fa0/3
   
     switchport mode access
   
     switchport access vlan 10

   - interface fa0/4

     switchport mode access

     switchport access vlan 10

   Configured Trunk Port (to router):

   - interface fa0/5

     switchport mode trunk

4. Router Configuration

   Enabled main interface:
   - interface fa0/0
     no shutdown

   Enabled sub-interfaces:
   
   - interface fa0/0.10
     
     encapsulation dot1q 10
     
     ip add 192.168.1.1 255.255.255.0

   - interface fa0/0.20

     encapsulation dot1q 20

     ip add 192.168.2.1 255.255.255.0

5. PC Configurations
   - PC1 (VLAN10): 192.168.1.11 / 255.255.255.0 / Gateway: 192.168.1.1
   - PC2 (VLAN10): 192.168.1.12 / 255.255.255.0 / Gateway: 192.168.1.1

   - PC3 (VLAN 20): 192.168.2.21 / 255.255.255.0 / Gateway: 192.168.2.1
   - PC4 (VLAN 20): 192.168.2.22 / 255.255.255.0 / Gateway: 192.168.2.1

6. Testing
   - Pinged from PC1 to PC3 (successful)
   - Verified connectivity using ping and ipconfig in the PCs




































