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
```
SERVER.py
     import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recieved".encode())
```
CLIENT.py
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
## OUTPUT

SERVER.py
![image](https://github.com/user-attachments/assets/19433ca6-c071-4ba2-b956-4eeb06b75202)

CLIENT.py
![image](https://github.com/user-attachments/assets/af8b76a7-3652-4e61-9d47-9580f0ac9120)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

