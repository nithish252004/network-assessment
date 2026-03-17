# Question 6
## Class Identification from IP Address

---

## Concepts Learned

### Class Identification
Class can be identified from the IP address by analyzing its first octet:

* **1-126:** * **Class A**
    * **Default mask:** 255.0.0.0
    * (127 is assigned for loopback i.e, if a computer needs to communicate to its local host)

* **128-191:** * **Class B**
    * **Default mask:** 255.255.0.0

* **192-223:** * **Class C**
    * **Default mask:** 255.255.255.0

### Examples

1) **10.1.1.1**
    * 10 (comes between 1-126), So class A
    * Default subnet mask : 255.0.0.0
    * Range : 1.0.0.0 – 126.255.255.255

2) **172.16.5.10**
    * 172 (comes between 128-191) , so class B
    * Default subnet mask : 255.255.0.0
    * Range : 128.0.0.0 to 191.255.255.255

3) **192.168.1.5**
    * 192 (comes between 192-223) , so class C
    * Default subet mask : 255.255.255.0
    * Range : 192.0.0.0 to 223.255.255.255

---
