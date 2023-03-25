## Armbian CMD Notes

### Getting all device status
```bash
nmcli device status
```

### Getting all device
```bash
nmcli dev wifi list
```

### Remove a package
```bash
sudo apt-get purge --auto-remove packagename
```

### checking ports and see who uses it.
```bash
sudo lsof -i -P -N
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
### Useful information - iptables
```bash
iptables -t [table] -OPTIONS [CHAIN] [matching component] [action component]

table (filter, nat, mangle, raw, security)
chains (prerouting, input, forward, output, postrouting)
options (A - append, D - delete, I - insert, R- replace, Z - zero counters, L-list, P  - policy, E - renamte, F - flush, N - new user defined chain, X - delete chain)

- matching component
-- p - protocol
-- s - source ip
-- d - destination ip
-- i - in interface
-- o - out interface

- action component
-j (accept, drop, reject, return)

```


### MK PPPOE Notifs
```:global DateTime ([ / system clock get date ] . " " . [ / system clock get time ]);

:local telegramToken "46109825455:AAEMr_M0lMmhztgWn6-wM-zRhOmfc4NT8Nc";

:local chatId "-3917804044";

:local adddress $"local-address";

/tool fetch url="https://api.telegram.org/bot$telegramToken/sendmessage?chat_id=$chatId&text=<<=====** Genman Server **=====>> %0A PPP Name: $user %0A IP Address: $address %0A Status: PPPOE Down %0A Last Seen: $DateTime %0A Message: Pls dispatch technical team if necessary. %0A <<======** Server Notif **======>>" keep-result=no;
```

