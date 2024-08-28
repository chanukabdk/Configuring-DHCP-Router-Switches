# Switch Configuration: Switch1

## Interface Configuration


# Enter global configuration mode
```plaintext
Switch> enable
Switch# configure terminal
```
# Configure interfaces connecting to Router1, Server, and PCs
```plaintext
Switch(config)# interface FastEthernet0/1
Switch(config-if)# description Connection to Router1
Switch(config-if)# switchport mode access
Switch(config-if)# no shutdown
Switch(config-if)# exit

Switch(config)# interface FastEthernet0/2
Switch(config-if)# description Connection to DHCP_Server1
Switch(config-if)# switchport mode access
Switch(config-if)# no shutdown
Switch(config-if)# exit

Switch(config)# interface FastEthernet0/3
Switch(config-if)# description Connection to PC1
Switch(config-if)# switchport mode access
Switch(config-if)# no shutdown
Switch(config-if)# exit

Switch(config)# interface FastEthernet0/4
Switch(config-if)# description Connection to PC2
Switch(config-if)# switchport mode access
Switch(config-if)# no shutdown
Switch(config-if)# exit
```
# Save the configuration
```plaintext
Switch# write memory
