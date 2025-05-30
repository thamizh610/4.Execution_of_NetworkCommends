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

## Output

NETSTAT

![image](https://github.com/user-attachments/assets/90a767a3-8587-4864-9959-a42f63f8c13c)

IPCONFIG

![image](https://github.com/user-attachments/assets/e9a41425-9e57-48dd-8245-950521aaf423)

PING

![image](https://github.com/user-attachments/assets/f8b8f4b1-c9ad-4817-8929-1428fbc08d10)

TRACERT

![image](https://github.com/user-attachments/assets/c7da7592-4482-4baa-9232-67f800a82332)

NSLOOKUP

![image](https://github.com/user-attachments/assets/7cfbc284-915a-4a60-bb56-df575b95fc1a)

GETMAC

![378099051-476c1334-6f03-4255-a726-201b431d06fc](https://github.com/user-attachments/assets/c4fc71f2-747b-423f-a8ad-67ad91ef8d95)

HOSTMAME

![378099139-7b52b169-cbe8-4b05-8acb-274f2c1566b5](https://github.com/user-attachments/assets/fb500420-273e-4cc7-8420-e147b4575c9a)

NBTSTAT

![378099417-98cd8d15-23a4-42da-93a1-4cb0c3714028](https://github.com/user-attachments/assets/6a4ca773-35f4-4c9b-8585-cf8bc5fd53ae)

ARP

![378099299-99653a10-3ff7-41da-a3cd-074fec878fc7](https://github.com/user-attachments/assets/479f9634-26d7-4a4a-9a4a-1e5722dfa6f1)

SYSTEMINFO

![378099556-9563669c-9e93-469d-a129-13ab5cc9b924](https://github.com/user-attachments/assets/906f9266-19ab-48fe-a910-3d77dba38596)

## Program

Client

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

Server

```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```

# Output

Tranceroute command

```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```

# Output

![image](https://github.com/user-attachments/assets/b504e554-42bc-400c-b8d4-22ba41d5ed5b)

## Result
Thus Execution of Network commands Performed 
