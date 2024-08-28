# Cisco Packet Tracer DHCP Server Project Configuration

## 1. Router Configuration

### Router: Router1

#### Interface Configuration
```plaintext
# Enter global configuration mode
Router> enable
Router# configure terminal

# Configure the interface connecting to the switch
Router(config)# interface GigabitEthernet0/0
Router(config-if)# ip address 192.168.10.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit

# (Optional) Disable the router's built-in DHCP service
Router(config)# no service dhcp
Router(config)# exit

# Save configuration
Router# write memory

