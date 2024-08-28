# Project Requirements: DHCP Configuration with a Dedicated DHCP Server

## Objective
Set up a network where a dedicated DHCP server dynamically assigns IP addresses to PCs. The goal is to ensure that all PCs receive their IP addresses automatically from the dedicated DHCP server, with the router handling routing tasks.

## Network Topology
- **Router**: Acts as the gateway and provides routing for the network.
- **Dedicated DHCP Server**: Provides dynamic IP addressing services.
- **Switch**: Connects all the PCs and the DHCP server to the network.
- **PCs**: End devices that will receive IP addresses from the DHCP server.

## Devices and Configuration

### Router
- **Name**: Router1
- **Interfaces**:
  - **GigabitEthernet0/0**: Connects to the switch.
  - **IP Address**: 192.168.10.1
- **Configuration Tasks**:
  - Disable the DHCP service on the router (to avoid conflicts).
  - Set up static routing if required.

### Dedicated DHCP Server
- **Name**: DHCP_Server1
- **Operating System**: Linux (e.g., Ubuntu Server) or Windows Server with DHCP role.
- **Network Configuration**:
  - **IP Address**: 192.168.10.2 (Static)
  - **Subnet Mask**: 255.255.255.0
  - **Default Gateway**: 192.168.10.1 (Router’s IP)
  - **DNS Server**: 8.8.8.8 (Google DNS or local DNS server)
- **DHCP Configuration**:
  - **DHCP Pool Name**: LAN_POOL
  - **Network Address**: 192.168.10.0
  - **Subnet Mask**: 255.255.255.0
  - **Default Gateway**: 192.168.10.1
  - **DNS Server**: 8.8.8.8
  - **Lease Time**: 24 hours
  - **IP Address Range**: 192.168.10.100 – 192.168.10.200
- **Additional Tasks**:
  - Exclude IP addresses from the pool that are assigned statically (e.g., for the router and DHCP server itself).

### Switch
- **Name**: Switch1
- **Ports Configuration**:
  - **FastEthernet0/1**: Connects to Router1 (GigabitEthernet0/0).
  - **FastEthernet0/2**: Connects to DHCP_Server1.
  - **FastEthernet0/3** to **FastEthernet0/6**: Connects to PCs.
- **VLAN Configuration** (optional):
  - **VLAN 10**: Used for the devices connected to the switch (if required).

### PC Configuration
- **PC1 to PC4**:
  - Set to obtain an IP address automatically via DHCP.

## Configuration Tasks

### Router Configuration
1. Assign a static IP address to the router interface.
2. Disable the router's built-in DHCP service.
3. Configure routing settings if required to allow communication between networks or the internet.

### Dedicated DHCP Server Configuration
1. Install and configure DHCP services on the server.
2. Set up the DHCP pool with the required parameters (IP range, subnet mask, gateway, DNS, etc.).
3. Ensure that the server has a static IP address outside of the DHCP pool.

### Switch Configuration
1. Connect all devices (router, DHCP server, PCs) to the switch.

### PC Configuration
1. Set each PC’s network adapter to obtain an IP address automatically from the DHCP server.

## Connectivity Testing
1. Verify that each PC successfully receives an IP address from the DHCP server.
2. Test connectivity between all PCs, the DHCP server, and the router.
3. Ensure that each PC can access external networks (e.g., the internet) if a connection is available.

## Deliverables
- **Network Diagram**: A visual representation of the network topology.
- **Configuration Files**: Text files or screenshots of the router, DHCP server, and switch configurations.
- **Testing Documentation**: Evidence of successful IP address assignment and network connectivity, including screenshots or command outputs.

## Additional Notes
- **Command Line Only**: Use the CLI for configuring the DHCP server, router, and switch where applicable. Avoid graphical configuration tools.
- **Documentation**: Ensure that all configurations are well-documented and clearly annotated.
- **Testing**: Perform thorough testing to confirm that all PCs receive IP addresses from the DHCP server and can communicate as expected.
