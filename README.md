# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## Program:
### CLIENT:
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```

### SERVER:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
### TRACE:
```
from scapy.all import*     
target = ["www.google.com"]     
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output
### ping:
![WhatsApp Image 2025-05-10 at 12 54 52_81acac92](https://github.com/user-attachments/assets/43696fbb-2d54-41c9-bb36-2eba7fc9dd9d)
### traceert:
![WhatsApp Image 2025-05-10 at 13 02 41_52070dbc](https://github.com/user-attachments/assets/17228333-d019-42dd-9cea-31522fe7bc5e)
### ipconfig:
![WhatsApp Image 2025-05-10 at 13 05 01_24e73f74](https://github.com/user-attachments/assets/557e4876-1623-4cdc-ad1b-5ecf0d6c314f)
### nbstat:
![WhatsApp Image 2025-05-10 at 13 05 43_bcdbd263](https://github.com/user-attachments/assets/deb1400d-d9c4-478e-bb79-e5838dadb172)
### nslookup:
![WhatsApp Image 2025-05-10 at 13 06 14_2ad79785](https://github.com/user-attachments/assets/8598ab14-ed50-4838-a15e-979e6cf98707)
### hostname:
![WhatsApp Image 2025-05-10 at 13 07 29_2769afb2](https://github.com/user-attachments/assets/fa7f7b32-05d7-49a5-b2b3-77aca2e3c6f1)
### netstat:
![WhatsApp Image 2025-05-10 at 13 08 23_8a439546](https://github.com/user-attachments/assets/26c6c2ee-a93c-482b-a0b2-4934ba4c3d81)
### getmac:
![WhatsApp Image 2025-05-10 at 13 09 07_f2fd9cc7](https://github.com/user-attachments/assets/635930fd-15d6-4d5d-bcf0-f96ec43513e6)
## Result
Thus Execution of Network commands Performed 
