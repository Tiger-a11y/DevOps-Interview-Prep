# Linux Networking Fundamentals

## Introduction
Linux networking is an essential skill for system administrators, providing the foundation for communication between devices, servers, and networks. Understanding Linux networking enables administrators to configure and manage systems efficiently, troubleshoot network issues, and ensure security. This document outlines fundamental networking concepts in Linux, covering key areas like network interfaces, IP addressing, DNS, routing, and network troubleshooting.

---

## 1. Network Interfaces in Linux
Network interfaces are the points through which Linux systems communicate over networks. A system can have multiple types of network interfaces, each serving different roles.

- **Physical Interfaces**: These are hardware-based interfaces, such as:
  - **Ethernet (eth0, enp0s3)**: Wired network connection.
  - **Wi-Fi (wlan0, wlp3s0)**: Wireless network connection.
- **Virtual Interfaces**: Logical network interfaces used for specific purposes:
  - **Loopback (lo)**: A virtual network interface used for internal communication within the system.
  - **Bridges (br0)**: Used in virtualized environments or network interfaces that combine multiple physical interfaces.
  - **VLANs (Virtual Local Area Networks)**: Logical partitions within a network that can isolate traffic between devices.
- **Network Namespaces**: Allow for network isolation in containers or virtualized environments. Each namespace can have its own interfaces, routing tables, and firewall settings.

### Commands to List Interfaces
```sh
ip link show      # List all network interfaces and their statuses
ifconfig -a       # Older method (deprecated in favor of the ip command)
nmcli device      # NetworkManager tool for managing connections
```  

---

## 2. IP Addressing and Configuration
IP addressing is the process of assigning unique identifiers to each device on a network. This allows for proper communication and routing of data across networks.

### Viewing IP Addresses
```sh
ip addr show      # Display the IP addresses assigned to each interface
hostname -I      # Show only the IPs of the system
```  

### Assigning an IP Address Manually
You can configure an IP address statically on a network interface using the following command:
```sh
sudo ip addr add 192.168.1.100/24 dev eth0
```

### DHCP vs. Static IP
- **DHCP (Dynamic Host Configuration Protocol)**: Automatically assigns IP addresses to devices from a DHCP server. Ideal for client devices that do not require fixed IP addresses.
- **Static IP**: A manually assigned, fixed IP address used for servers or devices requiring a predictable network presence.

To configure a static IP on Debian-based distributions, edit the `/etc/network/interfaces` file:
```ini
iface eth0 inet static
    address 192.168.1.100
    netmask 255.255.255.0
    gateway 192.168.1.1
```

---

## 3. DNS (Domain Name System)
DNS is a critical system that translates human-readable domain names (e.g., google.com) into IP addresses that systems use for communication.

### Checking DNS Configuration
```sh
cat /etc/resolv.conf   # Display the configured DNS servers
nslookup google.com    # Manually query a DNS server
dig google.com         # Perform a more detailed DNS lookup
```  

### Changing DNS Servers
You can update DNS servers to use faster or more reliable ones, like Google's DNS:
```sh
echo "nameserver 8.8.8.8" | sudo tee /etc/resolv.conf
```

---

## 4. Routing and Default Gateway
Routing defines how network packets are forwarded between devices on a network. The default gateway is the device that forwards traffic from your network to other networks, including the internet.

### Viewing the Routing Table
```sh
ip route show  # Display the routing table and current routing paths
```  

### Adding a Default Gateway
The default gateway forwards network packets when the destination IP is outside the local subnet:
```sh
sudo ip route add default via 192.168.1.1 dev eth0
```

---

## 5. Network Troubleshooting Tools
To diagnose network problems and ensure proper communication between devices, Linux provides several tools:

### **Ping**: Check network connectivity
```sh
ping 8.8.8.8  # Check if a host is reachable (Google's DNS server)
```

### **Traceroute**: Trace the route packets take to reach a destination
```sh
traceroute google.com  # Shows the path taken to reach google.com
```

### **Netstat**: Display active network connections
```sh
netstat -tulnp  # Show active connections and listening ports
```

### **TCPDump**: Capture and analyze network traffic
```sh
sudo tcpdump -i eth0  # Capture all packets on the eth0 interface
```

---

## 6. Firewall Management (iptables / nftables)
A firewall is essential for controlling network traffic. Linux offers two tools for firewall management:

- **iptables**: The legacy tool for configuring the firewall.
- **nftables**: The newer, more efficient tool that replaces iptables on modern systems.

### Checking Firewall Rules
```sh
sudo iptables -L -v   # List current iptables rules
sudo nft list ruleset  # List nftables rules
```  

### Allow SSH Traffic
To allow incoming SSH traffic on port 22:
```sh
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

### Block an IP Address
To block an IP address from accessing the system:
```sh
sudo iptables -A INPUT -s 192.168.1.50 -j DROP
```

---

## 7. Network Services and Ports
Many services on Linux systems rely on specific ports to function properly. Understanding these ports helps in managing network services and firewall configurations.

Common ports:
- **SSH (22)**: Secure remote login.
- **HTTP (80)**: Standard web traffic.
- **HTTPS (443)**: Secure web traffic.
- **DNS (53)**: Domain name resolution.
- **FTP (21)**: File Transfer Protocol.

### Checking Listening Ports
To check which services are currently listening on which ports:
```sh
ss -tulnp  # Advanced alternative to netstat
```

---

### Further Reading
For a more comprehensive understanding of Linux networking, consider exploring these manual pages:
- **Networking Tools**: `man ip`, `man netstat`, `man tcpdump`
- **Firewall Configuration**: `man iptables`, `man nft`
- **DNS and Routing**: `man resolv.conf`, `man route`

---