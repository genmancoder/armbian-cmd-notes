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
