Network services, environmen
===
#### What is managing networking
    systemctl is-active NetworkManager systemd-networkd

#### Inspect interfaces
    ip -br addr
    ip -br route

## With systemd-networkd  
(see: /etc/netplan/)
#### List active interfaces 
    networkctl atatus eth0
    
## With NetworkManager  
(see: /etc/NetworkManager/, /etc/NetworkManager/system-connections/)
#### List active interfaces 
    nmcli connection show
    nmcli connection show --active
    nmcli connection show "<connection-name>"
