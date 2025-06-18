# CCNA---EIGRP-LAB
In this lab, we have users located in two different subnets. For these users to communicate with each other, their data must be routed through the default gateways and the intermediate routers, which are also on different subnets.

To enable this communication, we will implement EIGRP (Enhanced Interior Gateway Routing Protocol) — a distance vector dynamic routing protocol.

**Step 1: IP Configuration**<br>
First, assign IP addresses to all devices and interfaces as shown in the network diagram. Ensure each subnet and its respective default gateway are correctly configured.

**Step 2: EIGRP Configuration on Routers**<br>
Next, we configure EIGRP on each router. This is done in global configuration mode: 
<br>**For example:**<br>
R2(config)# Router EIGRP 100
R2(config)# network 10.10.10.0 0.0.0.255
R2(config)# network 192.168.1.0 0.0.0.255

**100** is the Autonomous System (AS) number and must be the same on all routers participating in EIGRP.
**0.0.0.255** is the wildcard mask, which identifies the subnet range.

**Step 3: Routing Table and Neighbor Discovery**<br>
Once EIGRP is properly configured, the routers will automatically discover their neighbors and exchange routing information. This allows them to populate their routing tables with all connected and remote networks.

**Step 4: Verification**<br>
After successful configuration, you should be able to ping devices in the 192.168.2.0 network from devices in the 192.168.1.0 network, confirming inter-subnet connectivity through EIGRP.

_Note: This document has been formatted and paraphrased with the assistance of AI for clarity and structure._
