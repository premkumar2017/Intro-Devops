

---

# **Basic Networking Concepts for Students**

## **1. Introduction to Networking**
A **computer network** is a group of interconnected computers that communicate with each other to share resources, data, and applications. Each device in a network is assigned an **IP address**, which serves as its unique identifier.

### **Types of Networks**
1. **Personal Area Network (PAN)** – Small network for personal use (e.g., Bluetooth).

![image](https://github.com/user-attachments/assets/e5d3d37f-c838-4916-a2b0-1961264eafb2)



2. **Local Area Network (LAN)** – Covers a small geographic area like a home, office, or school.

![image](https://github.com/user-attachments/assets/ac793c5d-b451-4905-9af8-965560b5ca6e)



3. **Metropolitan Area Network (MAN)** – Covers a city or town.

![image](https://github.com/user-attachments/assets/99c34bf6-e75a-433e-8ac8-46aa66414b91)



4. **Wide Area Network (WAN)** – Spans large areas like countries or continents (e.g., the Internet).

![image](https://github.com/user-attachments/assets/693ce589-84cb-46df-a609-affaf583ff06)





5. **Virtual Private Network (VPN)** – Secures private communications over public networks.



![image](https://github.com/user-attachments/assets/eb2f5dc9-5a63-495c-b0b6-566bdf80736c)


---

## **2. OSI and TCP/IP Models**
### **OSI Model (7 Layers)**

![image](https://github.com/user-attachments/assets/1419f69e-76ca-4e9d-a73c-fdec35976515)


1. **Physical Layer** – Deals with physical transmission (e.g., cables, radio waves).
2. **Data Link Layer** – Handles MAC addressing and error detection.
3. **Network Layer** – Manages IP addressing and routing.
4. **Transport Layer** – Ensures reliable communication using TCP/UDP.
5. **Session Layer** – Maintains communication sessions.
6. **Presentation Layer** – Converts data formats (e.g., encryption).
7. **Application Layer** – Provides network services to users (e.g., HTTP, FTP).

### **TCP/IP Model (4 Layers)**

![image](https://github.com/user-attachments/assets/a28a325e-1925-4d2e-b520-3345bdf23af3)



1. **Network Access Layer** – Combines OSI’s Physical & Data Link layers.
2. **Internet Layer** – Equivalent to OSI’s Network Layer (IP addressing & routing).
3. **Transport Layer** – Uses TCP (reliable) or UDP (fast but unreliable).
4. **Application Layer** – Includes HTTP, FTP, SMTP, etc.

---

## **3. IP Addressing and Subnetting**
An **IP address** is a numerical label assigned to each device connected to a network.

### **IPv4 Address Classes**
| Class | Range | Default Subnet Mask | No. of Networks | No. of Hosts |
|--------|--------------|----------------|--------------|--------------|
| A | 1.0.0.0 - 126.255.255.255 | 255.0.0.0 | 128 | 16 million |
| B | 128.0.0.0 - 191.255.255.255 | 255.255.0.0 | 16,384 | 65,536 |
| C | 192.0.0.0 - 223.255.255.255 | 255.255.255.0 | 2 million | 256 |
| D | 224.0.0.0 - 239.255.255.255 | - | Multicast | - |
| E | 240.0.0.0 - 255.255.255.255 | - | Reserved | - |

### **Private vs Public IP Addresses**
- **Private IPs:** Used within a LAN (e.g., 192.168.x.x, 10.x.x.x, 172.16.x.x).
- **Public IPs:** Routable on the Internet, assigned by ISPs.

### **Subnetting**
Subnetting divides a large network into smaller networks.

- **Subnet Mask:** Defines network and host portions.
- **CIDR Notation:** `/8`, `/16`, `/24` indicate how many bits are for the network.
- Example:  
  - `192.168.1.0/24` (Subnet mask: 255.255.255.0) → 256 total IPs, 254 usable.
  - `192.168.1.0/26` (Subnet mask: 255.255.255.192) → 64 total IPs, 62 usable.

---

## **4. Network Devices**
### **Router**
- Connects different networks.
- Uses IP addresses to route data.
- Example: Home router connects your LAN to the Internet.

### **Switch**
- Connects devices within a LAN.
- Uses MAC addresses to forward data efficiently.

### **Firewall**
- Security device that filters network traffic.

---

## **5. Common Networking Protocols**
| Protocol | Function |
|----------|---------|
| TCP | Reliable, connection-oriented data transfer |
| UDP | Fast, connectionless data transfer |
| HTTP/HTTPS | Web browsing |
| FTP | File transfer |
| DHCP | Automatically assigns IP addresses |
| DNS | Resolves domain names to IPs |

---

## **6. Subnetting Practice**
### **Example 1:**
- Given: **192.168.1.0/26**
- Subnet Mask: **255.255.255.192**
- **Network ID:** `192.168.1.0`
- **Broadcast Address:** `192.168.1.63`
- **Usable IPs:** `192.168.1.1` to `192.168.1.62`
- **Total Hosts:** 64, **Usable Hosts:** 62

### **Example 2:**
- Given: **10.0.0.0/30**
- **Subnet Mask:** `255.255.255.252`
- **Usable IPs:** 2 (for point-to-point links)
- 


## **6. Types of Routing**

### **Types of Routing:**  

1. **Static Routing:**  
   - A technique where the network administrator manually adds routes to the routing table.  
   - It does not change automatically if the network topology changes.  
   - Suitable for small, stable networks with minimal route changes.  

2. **Default Routing:**  
   - A method where a router is configured to forward all packets to a predetermined next-hop device, regardless of the destination network.  
   - Commonly used when a router has only one exit path to an external network (e.g., connecting a local network to the internet).  

3. **Dynamic Routing:**  
   - A routing technique that uses dynamic protocols (e.g., RIP, OSPF, BGP) to automatically discover and update routes.  
   - Adapts to network topology changes without manual intervention.  
   - Suitable for large and complex networks.  



---

This content provides students with a fundamental understanding of networking, including subnetting and host details. Let me know if you need additional explanations or exercises! 🚀
