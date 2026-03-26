# Question 4,5,6
---




## Output Screenshot

Topology created in CISCO PACKET TRACER

![OP1](./4.1.png)

Configuration of Switch0 (Setting up access port and trunk ports)

![OP2](./4.2.png)

Configuration of Switch1 (with Access Ports and Trunk Ports)

![OP3](./4.3.png)

Configuring the routers and creating a subinterfaces for vlans

![OP4](./4.4.png)

Testing Same VLAN communication by setting up the access ports

From PC0 TO PC2 (Same VLAN)

![OP5](./4.5.png)


Pinging Different VLANs via router on a switch (Trunk ports)

From PC0 to PC1 (different VLANs but via port)

![OP6](./4.6.png)

Switch0 Vlan access and trunk ports configurations

![OP7](./4.7.png)

Switch1 Access and trunk ports configurations

![OP8](./4.8.png)

NATIVE VLAN

We can use the NATIVE VLAN as VLAN 99

On Switch0

![OP9](./4.9.png)

ON switch1

![OP10](./4.10.png)


Now if we intentionally change the Switch1 native vlan to 1 (before 99), the VLAN mismatch will be found

![OP11](./4.11.png)

We can check this using ,, show interfaces trunk

![OP12](./4.12.png)

In switch 1 Native vlan is set to 1

And in Switch 0

![OP13](./4.13.png)

it is set to 99

So Native VLAN mismatch is found. So Change the switch 1 NATIVE VLAN to 99 in order to resolve the mismatch issue.. 





