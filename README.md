# ROUTER-ON-STICK
INTER VLAN ROUTING ROUTER-ON-STICK
# Definition
Inter-VLAN routing is the process of enabling communication between different VLANs in a network. Router-on-a-Stick is a common method where a single router interface is divided into multiple subinterfaces, each corresponding to a VLAN, to route traffic between VLANs using a trunk link from the switch.
# project Definition
Inter-VLAN routing was implemented using a router-on-a-stick configuration to connect multiple LAN segments. The switch was configured with trunk links to carry VLAN traffic to the router. Three VLANs were created for different departments: VLAN10 for HR (gateway 192.168.10.1), VLAN20 for IT (gateway 192.168.20.1), and VLAN30 for Finance (gateway 192.168.30.1). The router was configured with sub-interfaces for each VLAN to enable inter-VLAN communication.


# CLI-COMMANDS

Router # config terminal

Router (config) # int gig 0/0/0.10

Router (config - subif) # encapsulation dot 1q 10

Router (config - subif) # ip address 192.168.10.1 255.255.255.0

Router (config - subif) # no shutdown

exit

Router (config) # int gig 0/0/0.20

Router (config - subif) # encapsulation dot 1q 20

Router (config - subif) # ip address 192.168.20.1 255.255.255.0

Router (config - subif) # no shutdown

exit

Router (config) # int gig 0/0/0.30

Router (config - subif) # encapsulation dot 1q 30

Router (config - subif) # ip address 192.168.30.1 255.255.255.0

Router (config - subif) # no shutdown

exit

Router # sh run

# INTER - VLAN ROUTING CLI - COMMANDS

Router # config terminal

Router (config) # int fa 0/1

Router (config - if) # switchport mode access

Router (config - if) # switchport access VLAN 10

**(all are same ------- 0/6 --- vlan commands)**

# VLAN - TRUNK

Router # config terminal

Router (config) # int fa 0/7

Router (config - if) # switchport mode access

Router (config - if) # switchport mode trunk
