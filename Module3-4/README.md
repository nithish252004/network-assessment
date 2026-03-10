# Question 8
## Ethernet Device Management and Networking Stack in Linux

---

This documentation covers the modular driver architecture of the Linux kernel, specifically focusing on how ethernet devices are managed through the networking stack.

---

## Concepts Learned

### 1. Networking Stack Architecture
The Linux kernel manages ethernet devices through a **modular driver architecture** and a layered networking stack. This system handles:
* **Packet Transmission:** Sending data from the stack to the hardware.
* **Packet Reception:** Receiving data from the hardware into the stack.
* **Interface Configuration:** Managing device states and settings.

### 2. Network Interface Representation
Network interfaces are represented by specific kernel structures and lifecycle functions:

* **`struct net_device`**: The core structure representing a network interface.
* **`alloc_netdev()`**: Function used for allocating the device structure.
* **`register_netdev()`**: Function used for registering the device with the kernel.

> **Note:** Drivers must initialize the device fully before registration to ensure system stability.

#### Safe Cleanup Process
To ensure a safe exit and prevent memory leaks, the following sequence is used:
1.  **`unregister_netdev()`**: Removes the device from the kernel registry.
2.  **`free_netdev()`**: Deallocates the memory used by the device structure.

---

### 3. Ethernet Driver Callbacks
Ethernet drivers must implement `struct net_device_ops` callbacks to handle operational tasks:

| Callback | Functionality | Locking Mechanism |
| :--- | :--- | :--- |
| `ndo_open()` | Device activation/start | `rtnl_lock` |
| `ndo_start_xmit()` | Packet transmission | `__netif_tx_lock` |
| `ndo_set_rx_mode()` | Multicast filtering & Promiscuous mode | N/A |



---

### 4. MTU and Frame Handling
The **MTU (Maximum Transmission Unit)** defines the maximum payload size (standard Ethernet is 1500 bytes, excluding headers). 

* **Symmetry:** MTU is enforced symmetrically for both RX (Reception) and TX (Transmission).
* **VLAN Support:** The stack supports VLAN tags, allowing frames up to **1518 bytes**.
* **DSA (Distributed Switch Architecture):** Specialized subsystems handle switch tagging, stripping protocols to deliver standard Ethernet frames to the stack via `netif_receive_skb()`.

---
