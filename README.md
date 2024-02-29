### 2a_Stop_and_Wait_Protocol:
### AIM:
To write a python program to perform stop and wait protocol
### ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
### PROGRAM:
## Clinet output:
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
## Server Output:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
### OUTPUT:
##  Client Output:
![Screenshot 2024-02-29 212951](https://github.com/DEVASANJAY002/2a_Stop_and_Wait_Protocol/assets/152069249/0258d43e-7a36-40ea-8b68-f66c38223c95)

## Server Output:
![Screenshot 2024-02-29 213003](https://github.com/DEVASANJAY002/2a_Stop_and_Wait_Protocol/assets/152069249/7c701867-4793-4789-8593-449794cbdb2e)
![Screenshot 2024-02-29 212937](https://github.com/DEVASANJAY002/2a_Stop_and_Wait_Protocol/assets/152069249/16a6df83-f005-425d-88b1-b7f90b2c3ab3)

### RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
