

---

# **Basic Networking Concepts for DevOps Engineer**

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

  ![image](https://github.com/user-attachments/assets/dccf643f-642b-4feb-a593-d7e2e021f5b2)


### **Switch**
- Connects devices within a LAN.
- Uses MAC addresses to forward data efficiently.

  ![image](https://github.com/user-attachments/assets/05777874-065f-43fe-abe8-ba8a824d0399)

---

## **5. Subnetting Practice**

![image](https://github.com/user-attachments/assets/25973873-65fd-442d-ab9b-3040b06a8e47)


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



### **7. What Does the Ping Command Do?**  

The **ping** command is a network utility used to test the connectivity between two network devices. It sends ICMP (Internet Control Message Protocol) echo request packets to a specified IP address or hostname and waits for a response. This helps determine:  
- Whether a device is reachable on the network.  
- The response time (latency) between the source and destination.  
- Packet loss, which indicates network issues.  

### **8. What is a NIC (Network Interface Card)?**  
A **Network Interface Card (NIC)** is a hardware component that enables a computer to connect to a network. It can be wired (Ethernet) or wireless (Wi-Fi).  

#### **Key Features of a NIC:**  
- Each NIC has a unique **MAC (Media Access Control) address**, which identifies the device on the network.  
- It allows communication between computers in a **Local Area Network (LAN)** or over the internet.  
- NICs are commonly used in **desktop computers, laptops, and servers** for network connectivity.  


Your definitions of **Public Address** and **Private Address** are mostly correct but could be refined for better clarity and readability. Here’s an improved version:  

---

### **9) Public Address**  
A **Public IP Address** (also known as an **external address**) is assigned by an **Internet Service Provider (ISP)** and is used to communicate outside the local network. It allows devices to access the internet and be reached from remote locations.  

#### **Key Characteristics:**  
- **Global Scope** – Public IP addresses are unique and can be accessed over the internet.  
- **Assigned by ISP** – Internet providers allocate public IP addresses.  
- **Not Free** – Public IPs are provided by ISPs at a cost.  
- **Enables Remote Access** – It allows external users to connect to a device or server inside the network (e.g., hosting a home server).  

---

### **10) Private Address**  
A **Private IP Address** (also known as an **internal address**) is used within a **Local Area Network (LAN)** to communicate between devices. It cannot be accessed directly from the internet and helps maintain network security.  

#### **Key Characteristics:**  
- **Local Scope** – Only used within a private network (e.g., home or office network).  
- **Used for LAN Communication** – Enables communication between devices like computers, printers, and smartphones inside a network.  
- **Free of Cost** – Private IPs do not require ISP allocation and are available for free.  
- **Not Routed on the Internet** – Traffic from the internet cannot directly reach private IP addresses.  
- **Finding Private IP Address** – Use the command `ipconfig` (Windows) or `ifconfig` (Linux/macOS) to view the private IP of your device.  

### **11) What is a Proxy Server?**  
**Ans:** A **proxy server** is an **intermediary** between a user's device and the internet. It forwards requests from clients to web servers and then returns the requested data to the client.  

### **Key Functions of a Proxy Server:**  
- **Hides the Client's IP Address** – Enhances privacy and security.  
- **Filters Web Content** – Blocks restricted websites and harmful content.  
- **Caches Data** – Speeds up web browsing by storing frequently accessed resources.  
- **Improves Security** – Acts as a firewall by preventing direct connections to potentially harmful sites.  
- **Provides Anonymity** – Helps users stay anonymous by masking their real IP address.  


### **What is a Firewall?**  

A **firewall** is a **network security system** that monitors and controls incoming and outgoing network traffic based on **predefined security rules**. It acts as a **barrier** between a trusted internal network (e.g., a company’s private network) and an untrusted external network (e.g., the internet).  

![image](https://github.com/user-attachments/assets/daf06065-e6d2-4834-9b4f-3995cece334a)


### **Functions of a Firewall:**  
✅ **Monitors network traffic** – Inspects data packets entering or leaving a network.  
✅ **Blocks unauthorized access** – Prevents hackers and malicious traffic from entering the system.  
✅ **Implements security policies** – Enforces rules to allow or deny specific types of traffic.  
✅ **Prevents malware attacks** – Detects and blocks suspicious activity.  
✅ **Filters content** – Restricts access to certain websites or applications.  

### **Types of Firewalls:**  
1️⃣ **Packet Filtering Firewall (Layer 4)** – Works at the network and transport layers, filtering packets based on IP addresses, ports, and protocols.  
2️⃣ **Stateful Inspection Firewall** – Monitors active connections and makes decisions based on connection states.  
3️⃣ **Proxy Firewall (Layer 5 - Application Gateway)** – Acts as an intermediary between users and the internet, filtering requests based on content.  
4️⃣ **Next-Generation Firewall (NGFW)** – Uses advanced features like deep packet inspection, intrusion detection, and threat intelligence.  



---

