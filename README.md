# Ex-2a Stop_and_Wait_Protocol
## Register Number: 212222230064
## Name: Kavinesh M
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### Client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
   print(ack)
   continue
 else:
   c.close()
   break
```
### Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
### Client:

![image](https://github.com/kavinesh8476/2a_Stop_and_Wait_Protocol/assets/118466561/63088808-8a1b-454e-8d00-0aa147307854)


### Server:

![image](https://github.com/kavinesh8476/2a_Stop_and_Wait_Protocol/assets/118466561/e54c3629-d1d1-4cc9-8fdc-195f1e8eabe9)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
