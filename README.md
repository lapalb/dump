# dump
Contains non relevant info that I wanna dump

---

```
iwconfig : Gived info about wireless adapter
ifconfig [interface name] down/up : Make the interface up/down
airmon-ng check kill
iwconfig [interface-name] mode monitor : Changes wireless mode from managed to monitor
ifconfig [interface-name] hw ether [Your_Desired_MAC_Adress]
airodump-ng [interface-name] : Sniffs all the wireless network around with their protection level(Open/WEP/WPA/WPA2) and other critical info
```

```
airodump-ng --band [a,b,g,n] [interface-name] : capture packet in band specified

airodump-ng --bssid [bssid] --channel [channel number]

aireplay-ng --deauth  100000 -a [access mac] -c [client mac] [interface-name]
```

