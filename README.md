# one_liner_bash

### cpu_name
linux 
```bash
grep 'model name' /proc/cpuinfo | uniq | sed 's/model name\t*\s:\s*//g'
```
windows
```bash
wmic cpu get Name | find /v \"Name\"
```

### check OS
linux
```bash
uname
```
windows
```bash
ver
```

### hostname
linux
```bash
hostname | sed 's/.virtuosgames.com//g' | tr '[:lower:]' '[:upper:]'
```
windows
```bash
wmic computersystem get name | find /v "Name"
```

### Ip address
linux
```bash
ip route get 8.8.8.8 | head -1 | cut -d' ' -f7
```
windows
```bash
netsh interface ip show address "Ethernet" | findstr "IP Address"
```

### Memory
linux
```bash
grep MemTotal /proc/meminfo | sed 's/[^0-9]//g'
```
windows
```bash
"wmic memphysical get MaxCapacityEx | find /v \"MaxCapacityEx\"
```
