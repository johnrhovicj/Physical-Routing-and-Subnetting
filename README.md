# Project 1: Physical Routing and Subnetting

## Project Overview

In this project, I created two separate local area networks (LAN) using Cisco Packet Tracer. The network was divided into two rooms: **Room A** and **Room B**. I used one router to allow communication between the two subnets.

## Network Topology

- **Room A Subnet:** `192.168.1.0/24`
  - Router Interface: `GigabitEthernet0/0`
  - Default Gateway: `192.168.1.1`

- **Room B Subnet:** `192.168.2.0/24`
  - Router Interface: `GigabitEthernet0/1`
  - Default Gateway: `192.168.2.1`

## Router Configuration

I used the following Cisco IOS commands to configure the router interfaces.

```text
enable
configure terminal

interface GigabitEthernet0/0
 ip address 192.168.1.1 255.255.255.0
 no shutdown
exit

interface GigabitEthernet0/1
 ip address 192.168.2.1 255.255.255.0
 no shutdown
exit

end
copy running-config startup-config
```

## PC Configuration

| Device | IP Address | Subnet Mask | Default Gateway |
|--------|------------|-------------|-----------------|
| PC1 (Room A) | `192.168.1.10` | `255.255.255.0` | `192.168.1.1` |
| PC2 (Room A) | `192.168.1.11` | `255.255.255.0` | `192.168.1.1` |
| PC3 (Room B) | `192.168.2.10` | `255.255.255.0` | `192.168.2.1` |
| PC4 (Room B) | `192.168.2.11` | `255.255.255.0` | `192.168.2.1` |

## Result

After configuring the router and setting the correct IP address and default gateway for each PC, the two subnets were able to communicate successfully.

During the first ping attempt, there was a **Request timed out** because of the ARP resolution process. After that, the following ping attempts were successful and the two networks were able to communicate properly.

## Author

**John Rhovic Juliado**