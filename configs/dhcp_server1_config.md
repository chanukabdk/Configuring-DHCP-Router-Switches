# Server Configuration: DHCP_Server1

## GUI Configuration

### 1. Add Server to Workspace
- Drag and drop the **Server** device onto the workspace from the **"End Devices"** section.

### 2. Configure DHCP Service
1. Click on the **Server** device.
2. Go to the **"Services"** tab.
3. Select **"DHCP"** from the left menu.
4. Toggle the DHCP service to **"On"**.
5. Fill out the DHCP configuration:
   - **Pool Name**: `DHCP-Pool`
   - **Default Gateway**: `192.168.10.1`
   - **DNS Server**: `8.8.8.8`
   - **Start IP Address**: `192.168.10.100`
   - **Subnet Mask**: `255.255.255.0`
   - **Maximum Number of Users**: `100`
6. Click **Add** to save the DHCP configuration.

### 3. Set Static IP for Server
1. Go to the **"Desktop"** tab.
2. Click on **"IP Configuration"**.
3. Set a static IP:
   - **IP Address**: `192.168.10.2`
   - **Subnet Mask**: `255.255.255.0`
   - **Default Gateway**: `192.168.10.1`
4. Ensure the **DHCP** option is turned off here.
