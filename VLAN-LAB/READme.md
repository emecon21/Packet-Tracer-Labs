## INTER-VLAN Routing and Trunking Configurations Lab
This lab is my practice on how to configure VLANs in Cisco Packet Tracer.
The goal is to separate devices into different networks (FINANCE and MARKETING), and then use a router (Router-on-a-Stick) to allow communication between them.


## Steps Followed
1. Network Topology Setup
   - One switch
   - One router
   - Four PCs (2 in FINANCE VLAN, 2 in MARKETING VLAN)

2. Creating VLANs on the Switch
   
   (VLAN 10 for FINANCE, VLAN 20 for MARKETING)
   - Entered global configuration mode: configure terminal
   - Created VLANs:
     (vlan 10
     name FINANCE
     vlan 20
     name MARKETING)

3. Assigning VLANs to Interfaces
   
   interface fa0/1
   
   switchport mode access
   
   switchport access vlan 10

Switch(config)# interface fa0/2
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10

Switch(config)# interface fa0/3
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 20

Switch(config)# interface fa0/4
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 20




































