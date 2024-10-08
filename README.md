# 4.Execution_of_NetworkCommands

### NAME : THARUN SRIDHAR
### REGISTER NO : 212223230230

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

## CODE

**CLIENT :**
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

**SERVER :**
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode()) 
```

**TRACER :**
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```

## Output

**TRACER :**
![image](https://github.com/user-attachments/assets/38a573f4-8007-4a98-a2c9-2fb9eed73e10)

**CLIENT :**
![image](https://github.com/user-attachments/assets/e47866f4-b8b1-46de-a2da-24b2428d8f18)

**SERVER :**
![image](https://github.com/user-attachments/assets/c4d862e4-da99-4734-8308-2554bbba9fd3)

## Result
Thus Execution of Network commands Performed 
