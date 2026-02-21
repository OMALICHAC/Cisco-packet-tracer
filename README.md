# Smart Home Network Simulation -- Cisco Packet Tracer

![Cisco Packet Tracer](https://img.shields.io/badge/Cisco-Packet%20Tracer-0076D6?style=for-the-badge&logo=cisco&logoColor=white)
![Networking](https://img.shields.io/badge/Networking-Home%20Network-2E8B57?style=for-the-badge)
![IoT](https://img.shields.io/badge/IoT-Smart%20Home-FF6F00?style=for-the-badge)
![Network Design](https://img.shields.io/badge/Network-Design%20%26%20Simulation-8A2BE2?style=for-the-badge)

---

## Table of Contents

- [What This Project Is](#what-this-project-is)
- [Why Smart Home Networking Matters](#why-smart-home-networking-matters)
- [Network Design](#network-design)
- [Network Topology Diagram](#network-topology-diagram)
- [Key Networking Concepts](#key-networking-concepts)
- [How to Open the Simulation](#how-to-open-the-simulation)
- [What to Explore](#what-to-explore)
- [Security Considerations](#security-considerations)
- [Tools Used](#tools-used)
- [Author](#author)
- [License](#license)

---

## What This Project Is

A smart home network I designed and simulated in **Cisco Packet Tracer**. The setup includes a gateway router, wireless access point, and several IoT devices (smart lights, thermostat, cameras, door lock) all connected and configured with proper IP addressing and wireless settings. Everything runs on a single simulation file so you can open it and poke around.

**Simulation file:** `MY PACKET TRACER - Copy.pkt`

---

## Why Smart Home Networking Matters

### IoT Security Challenges

- **Default credentials** -- Many IoT devices ship with factory-set passwords that are publicly documented and rarely changed.
- **Unencrypted traffic** -- Low-cost devices frequently transmit data in plaintext, exposing usage patterns and camera feeds.
- **Lateral movement** -- A compromised IoT device on a flat network can be a pivot point to personal computers and other high-value targets.
- **Firmware neglect** -- Consumer IoT devices often lack automatic updates, leaving known vulnerabilities unpatched for months or years.
- **Weak network segmentation** -- Most home networks place all devices on a single subnet with no isolation between trusted and untrusted endpoints.

---

## Network Design

The simulation models a typical residential smart home with the following network components:

| Component | Role |
|---|---|
| **Gateway Router** | Connects the home network to the ISP; provides NAT, DHCP, and firewall services |
| **Wireless Access Point** | Provides Wi-Fi connectivity for wireless devices throughout the home |
| **Smart Lights** | IoT-enabled lighting controlled via the network |
| **Smart Thermostat** | Network-connected climate control device |
| **Security Cameras** | IP-based surveillance cameras streaming over the local network |
| **Smart Door Lock** | IoT door lock managed remotely through the home network |
| **Home Server / PC** | Central computing device for management and monitoring |
| **Smartphones / Tablets** | Mobile endpoints used to control and monitor smart devices |

Each device is assigned an IP address via DHCP or static configuration and communicates over the shared home network infrastructure.

---

## Network Topology Diagram

```
                        +-----------------+
                        |    INTERNET     |
                        |   (ISP Cloud)   |
                        +--------+--------+
                                 |
                                 | WAN
                                 |
                        +--------+--------+
                        |  GATEWAY ROUTER |
                        |  (DHCP, NAT,    |
                        |   Firewall)     |
                        +--------+--------+
                                 |
                                 | LAN
                                 |
                   +-------------+-------------+
                   |                           |
          +--------+--------+        +---------+---------+
          |   HOME SERVER   |        |  WIRELESS ACCESS  |
          |   / DESKTOP PC  |        |      POINT        |
          +-----------------+        +---------+---------+
                                               |
                                               | Wi-Fi
                                               |
                +-----+-----+-----+-----+-----+-----+
                |     |     |     |     |     |      |
               [A]   [B]   [C]   [D]   [E]   [F]   [G]
```

**Legend:**

| Label | Device |
|-------|--------|
| [A] | Smart Lights |
| [B] | Smart Thermostat |
| [C] | Security Camera 1 |
| [D] | Security Camera 2 |
| [E] | Smart Door Lock |
| [F] | Smartphone |
| [G] | Tablet |

> **Note:** The exact topology may vary within the .pkt file. Open the simulation to explore the full layout and device interconnections.

---

## Key Networking Concepts

Networking concepts covered:

- **DHCP (Dynamic Host Configuration Protocol)** -- The gateway router assigns IP addresses dynamically to connected devices, handling address allocation without manual intervention.
- **Wireless Configuration (802.11)** -- The access point is configured with an SSID, security mode, and authentication parameters.
- **IoT Device Connectivity** -- Each smart device is registered on the network and communicates over TCP/IP.
- **IP Addressing and Subnetting** -- Devices are organized within a defined IP address range on a residential subnet.
- **Network Segmentation Concepts** -- The design highlights where segmentation boundaries should exist between IoT and personal computing devices.
- **Device Registration and Management** -- Smart devices are added to the network and configured to interact with one another.

---

## How to Open the Simulation

### Step 1: Install Cisco Packet Tracer

Cisco Packet Tracer is available for free through the Cisco Networking Academy.

1. Visit [Cisco Networking Academy](https://www.netacad.com/) and create a free account.
2. Enroll in the **"Getting Started with Cisco Packet Tracer"** course (free).
3. Download Cisco Packet Tracer for your operating system (Windows, macOS, or Linux).
4. Install and launch the application.

> **System Requirements:** Cisco Packet Tracer runs on Windows 10/11, macOS 10.14+, and Ubuntu 20.04+. A minimum of 4 GB RAM is recommended.

### Step 2: Open the Simulation File

1. Clone or download this repository:
   ```bash
   git clone https://github.com/your-username/Cisco-packet-tracer.git
   ```
2. Open Cisco Packet Tracer.
3. Go to **File > Open** and navigate to the downloaded repository folder.
4. Select **`MY PACKET TRACER - Copy.pkt`** and click Open.

### Step 3: Explore the Topology

Once the file loads, you will see the full smart home network topology displayed in the workspace. You can zoom in and out, click on individual devices, and interact with the simulation in real time.

---

## What to Explore

### Device Configurations
Click on any device in the topology to open its configuration panel. Examine:
- IP address assignments (static vs. DHCP)
- Default gateway settings
- Wireless interface parameters (SSID, channel, security mode)

### Connectivity Testing
Use the built-in tools to verify network connectivity:
1. Open the **Command Prompt** on any PC or server device.
2. Run `ping <target IP>` to test reachability between devices.
3. Use `ipconfig` (on PCs) to view current network configuration.
4. Try pinging from an IoT device to the gateway to confirm registration.

### IP Address Assignments
Navigate to the gateway router and examine the DHCP pool:
- What IP range is assigned to devices?
- Which devices received addresses via DHCP?
- Are any devices statically configured?

### Wireless Settings
Click on the wireless access point to review:
- SSID name and broadcast settings
- Security protocol (WPA2-PSK, WPA3, or open)
- Connected client list

### IoT Device Behavior
Interact with smart home devices to observe:
- How IoT devices communicate with the home server
- Data flow patterns between sensors and controllers
- Device state changes (e.g., turning a light on/off)

---

## Security Considerations

### Network Segmentation
The most effective defense for a smart home network is proper segmentation. IoT devices should be isolated from personal computing devices on a separate VLAN or subnet. A compromised smart bulb shouldn't be a stepping stone to a laptop with sensitive data.

**Recommended architecture:**
- **VLAN 10 -- Trusted Devices:** PCs, laptops, smartphones
- **VLAN 20 -- IoT Devices:** Smart lights, thermostats, cameras, locks
- **VLAN 30 -- Guest Network:** Visitor devices with internet-only access

### Credential Hardening
Every device on the network should have its default credentials changed immediately upon deployment. This includes:
- Router admin panel username and password
- Wireless access point management credentials
- IoT device companion app accounts
- Any web-based management interfaces

### Firmware and Software Updates
IoT devices should be checked regularly for firmware updates. Many manufacturers release patches for critical vulnerabilities, but devices rarely update themselves. Establishing a maintenance schedule is essential.

### Traffic Monitoring
Monitoring network traffic from IoT devices can reveal anomalous behavior such as:
- Unexpected outbound connections to unknown IP addresses
- High-volume data transfers from devices that should produce minimal traffic
- DNS queries to suspicious or newly registered domains

### Encryption
Where possible, ensure that communication between IoT devices and their cloud services uses TLS/HTTPS. Devices that transmit data in cleartext should be flagged and either replaced or placed behind additional network controls.

---

## Tools Used

| Tool | Purpose |
|---|---|
| **Cisco Packet Tracer** | Network simulation and topology design |

---

## Author

**Chioma Iroka**
Computer Science Graduate | Cybersecurity Focus
- GitHub: [github.com/ChiomaIroka](https://github.com/ChiomaIroka)

---

## License

This project is released under the [MIT License](LICENSE).
