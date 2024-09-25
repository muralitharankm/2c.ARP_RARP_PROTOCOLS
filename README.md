# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
```py
import socket
s=socket.socket()
s.bind(('localhost',8880))
s.listen(5)
c,addr=s.accept()
address={"192.168.144.56":" AC:50:DE:1B:DE:65"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())

```
## OUPUT - ARP
![Screenshot 2024-09-25 154718](https://github.com/user-attachments/assets/a7d4f67a-97be-4976-afae-e2257c8c413a)

## PROGRAM - RARP
```py
import socket
s=socket.socket()
s.connect(('localhost',8880))
while True:
    ip=input("Enter Logical Address:")
    s.send(ip.encode())
    print("MAC address",s.recv(1024).decode())

```

## OUPUT -RARP
![Screenshot 2024-09-25 154739](https://github.com/user-attachments/assets/1bdb61b5-6246-4d76-a1d4-afd2bd7476eb)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
