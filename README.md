# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
## Algorithm for Server Program

1. Start

2. Import socket library

3. Create a socket using socket()

4. Bind the socket to address 'localhost' and port 8001

5. Listen for incoming connections

6. Display "Waiting for connection..."

7. Accept the client connection

8. Display connected client address

9. Repeat the following steps:

   • Receive message from client

   • If message is "exit"

        • Display "Client disconnected"

        • Exit loop

   • Display client message

   • Get reply from server user

   • Send reply to client

10. Close client socket

11. Close server socket

12. Stop

## Algorithm for Client Program

1. Start

2. Import socket library

3. Create a socket using socket()

4. Connect to server using 'localhost' and port 8001

5. Repeat the following steps:

   • Get message from user

   • Send message to server

   • If message is "exit"

       • Display "Disconnected"

       • Exit loop

   • Receive reply from server

   • Display server reply

6. Close socket

7. Stop
## PROGRAM
## Server.py
```
import socket
s=socket.socket()
s.bind(('localhost', 8001))
s.listen(1)
print("Waiting for connection...")
c, addr=s.accept()
print("Connected to", addr)
while True:
    clientMessage=c.recv(1024).decode()
    if clientMessage=="exit":
        print("Client disconnected")
        break
    print("Echo of Client >", clientMessage)
    reply = input("Server > ")
    c.send(reply.encode())
c.close()
s.close()
```
## Client.py
```
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    msg=input("Client > ")
    s.send(msg.encode())
    if msg=="exit":
        print("Disconnected")
        break
    print("Echo of Server >", s.recv(1024).decode())
s.close()
```
## OUPUT
![alt text](<Screenshot 2026-03-13 180254.png>)
## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
