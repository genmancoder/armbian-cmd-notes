## Armbian CMD Notes

### Getting all device status
```bash
nmcli device status
```

### Getting all device
```bash
nmcli dev wifi list
```

### Setting up predictable names = /boot/ArmbianEnv.txt
```bash
extraargs=net.ifnames=0
```

### Setting up interfaces = /etc/network/interfaces
```bash
auto br0
iface br0 inet static
        address 10.0.0.1
        netmask 255.255.240.0
        bridge_ports wlan0 eth1 eth2 eth3 eth4 eth0.10
        network 10.0.0.0
        broadcast 10.10.15.255

```
