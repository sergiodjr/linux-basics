|<< ADAPTER >>|
|-------------|

*Check interface configuration*
```
cat /etc/network/interfaces
```

*Identify the Network Interface:*
```
ip a
```

*Verifying the Interface Status*
```
ip addr show <INTERFACE_NAME>
```

*Set interface status DOWN/UP*
```
sudo ip link set <interface_name> down
```

```
sudo ip link set <INTERFACE_NAME> up
```

*Check dmesg for errors related to the interface*
```
dmesg | grep  <INTERFACE_NAME>
```

<br>
<br>


|<< GATEWAY >>|
|-------------|

*Default gateway*
```
ip route | grep default
```

*Replace default route temporary - It will reset after restart/shutdown*
```
sudo ip route replace default via <IP> dev <INTERFACE_NAME>
```

*Delete default route*
```
sudo ip route del default via <IP>
```

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

*Restart networks adapters and settings*
```
sudo systemctl restart networking
```

```
sudo systemctl enable networking
```

<br>
<br>
