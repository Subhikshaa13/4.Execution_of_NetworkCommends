# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:

In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 

All commands related to Network configuration which includes how to switch to privilege mode

and normal mode and how to configure router interface and how to save this configuration to

flash memory or permanent memory.

This commands includes

• Configuring the Router commands

• General Commands to configure network

• Privileged Mode commands of a router 

• Router Processes & Statistics

• IP Commands

• Other IP Commands e.g. show ip route etc.

### Program:
Client:
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
Server:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
Traceroute command:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output
![330674630-007703f5-9deb-4114-ad66-620b328ff7c0](https://github.com/Subhikshaa13/4.Execution_of_NetworkCommends/assets/118787344/4345fa36-a3fa-4bec-886d-4d73e90d3552)
![330674654-87be1fb2-4958-46fb-8333-b12a5a1dfd5d](https://github.com/Subhikshaa13/4.Execution_of_NetworkCommends/assets/118787344/0818a550-8744-420c-8aca-3a066070f5d1)
![330674697-6d763869-698e-4ce4-985b-064d54e660b2](https://github.com/Subhikshaa13/4.Execution_of_NetworkCommends/assets/118787344/b9a5471a-60b4-40a1-90ad-5c6a528a193d)

## Result
Thus Execution of Network commands Performed 
