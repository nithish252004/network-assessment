# Question 4
## You are given three IP addresses: 192.168.10.5, 172.20.15.1, and 8.8.8.8.
## 1.	Identify the class of each IP address.
## 2.	Determine if it is private or public.
## 3.	Explain how NAT would handle a private IP when accessing the internet.


---

## 1)	Identify the class of each IP address
The classes are identified based on the first octet range of classes . 

(1 – 126 ) : Class A

(128 – 191) : Class B

(192 – 223) : Class C

Private IP ranges : 

For class A (10.0.0.0 – 10.255.255.255)

For class B (172.16.0.0 – 172.31.255.255)

For class C (192.168.0.0 – 192.168.255.255)



1)	Given IP : 192.168.10.5

      Class C ( first octet comes in the range between 192-223)

      Subnet mask is 255.255.255.0

      192.168.x.x ( Private IP Address)
  	
2)	Given IP : 172.20.15.1

     Class B ( first octet comes in the range between 128-191)

      Subnet mask is 255.255.0.0

      172.20.x.x (in the range of 172.16.x.x to 172.31.x.x) ( Private IP Address)
  

3)	Given IP : 8.8.8.8 (Google DNS Server)
   
       Class A ( first octet comes in the range between 1-126)
  	
  	   Subnet mask is 255.0.0.0
  	
  	   Not in a range of 10.0.0.0 – 10.255.255.255, So it is a public IP address.




## 3)Explain how NAT handles a Private IP when accessing the internet.

Private IP addresses cannot be used on the internet. 

For example , I have my IP 192.168.10.5 ..  if this address goes to the internet , routers will drop the packets, because private IPs are not routable globally.

In order to make the private IPs communicate with the internet , NAT (Network Address Translation) is used. 

NAT : Converts Private IPs to Public IPs

Before NAT

MY PC:

192.168.10.5 wants to access 8.8.8.8

Packet leaving PC:

Source IP = 192.168.10.5

Destination IP = 8.8.8.8

Router performs NAT

Router replaces the private IP with its public IP.

Eg: 49.204.10.25 and store it in a NAT table. And this IP will become as a source IP in order to communicate with the internet.

Now packet becomes:

Source IP = 49.204.10.25

Destination IP = 8.8.8.8

When reply comes back

Source = 8.8.8.8

Destination = 49.204.10.25

Router checks its NAT table and translates back:

Destination → 192.168.10.5

