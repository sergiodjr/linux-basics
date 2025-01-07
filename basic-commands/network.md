|<< ADAPTER >>|
|-------------|
<br>

*Check interface configuration*
```
cat /etc/network/interfaces
```
<br>

*Identify the Network Interface:*
```
ip a
```
<br>

*Verifying the Interface Status*
```
ip addr show <INTERFACE_NAME>
```
<br>

*Set interface status DOWN/UP*
```
sudo ip link set <INTERFACE_NAME> down
```

```
sudo ip link set <INTERFACE_NAME> up
```
<br>

*Check dmesg for errors related to the interface*
```
dmesg | grep  <INTERFACE_NAME>
```
<br>

*Interface setting sample*
```
# This file describes the network interfaces available on your system
# and how to activate them.

source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

auto enp2s0
iface enp2s0 inet static
 address 192.168.5.200
 netmask 255.255.255.0
 gateway 192.168.5.111
```
<br>

|<< GATEWAY >>|
|-------------|
<br>

*Default gateway*
```
ip route | grep default
```
<br>

*Replace default route temporary - It will reset after restart/shutdown*
```
sudo ip route replace default via <IP> dev <INTERFACE_NAME>
```
<br>

*Delete default route*
```
sudo ip route del default via <IP>
```
<br>

*Permanent network settings*
```
sudo nano /etc/network/interfaces
```

```
auto <INTERFACE_NAME>
iface <INTERFACE_NAME> inet static
    address <IP>
    netmask <IP>
    gateway <IP>
```
<br>

*Restart networks adapters and settings*
```
sudo systemctl restart networking
```
<br>

*Enable networks adapters and settings*
```
sudo systemctl enable networking
```
<br>
