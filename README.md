# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM:
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM:
### SERVER:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print('Connected by', addr)
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
### CLIENT:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message to send to server: ")
        s.sendall(message.encode())
        data = s.recv(1024)
        print('Received', repr(data.decode()))

```
## OUPUT:
### SERVER:
![Screenshot 2024-04-03 104440](https://github.com/Rogith08/3b_CHAT_USING_TCP_SOCKETS/assets/162728044/3f9bbfef-ba56-4634-b602-a337569ab781)

### CLIENT:
![Screenshot 2024-04-03 104502](https://github.com/Rogith08/3b_CHAT_USING_TCP_SOCKETS/assets/162728044/9cd84007-2457-4e41-8559-c836c3cce5fa)

## RESULT:
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
