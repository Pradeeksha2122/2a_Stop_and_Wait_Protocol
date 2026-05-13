# 2a_Stop_and_Wait_Protocol
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
## Server:
```
import socket


s = socket.socket()


s.bind(('localhost', 8000))

s.listen(5)

print("Server waiting for connection...")


c, addr = s.accept()
print("Connected with:", addr)

while True:
   
    i = input("Enter a data: ")
    c.send(i.encode())

    
    ack = c.recv(1024).decode()

    if ack:
        print("Client says:", ack)
        continue
    else:
        c.close()
        break
## Client:
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode()) 
``
## OUTPUT

## Server
<img width="1142" height="493" alt="image" src="https://github.com/user-attachments/assets/61fac723-0b36-4fd2-b86a-411aeba3ec9a" />

## Client
<img width="1062" height="498" alt="image" src="https://github.com/user-attachments/assets/5d0ad369-761d-49e9-ae0b-5a115c8800b5" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
