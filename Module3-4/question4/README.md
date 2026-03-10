# Question 4
## Troubleshoot ethernet communication using ping and traceroute. Using cisco packet tracer.

---


## Output Screenshot

### Used 2 PC's , 2 Switches and one router in order to demonstrate this.

### Router Configuration in Cisco Packet Tracer
![OP1](./4.1.png)

### Checking if the Network is reachable or not
![OP2](./4.2.png)

### Used TraceRoute in order to identify the Packet Flow (HOPS)
![OP3](./4.3.png)

### Removed the Default Gateway from PC0 in order to perform troubleshooting
![OP4](./4.4.png)

### TraceRoute After removed the default gateway
![OP5](./4.5.png)


### Conclusion
PC0  is sending packets.. but it is not even reached the first hop properly. So we can identify that there is an issue with the local configuration of the system. 

