# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program

## PROGRAM
### SERVER SIDE
```
import socket
s=socket.socket()
s.bind(('localhost',9999))
s.listen(1)
print("server listening...")
conn,addr=s.accept()
print(f"connected to {addr}")

while True:
    frames= conn.recv(1024).decode()
    if not frames:
        break
    
    print(f"received frames: {frames}")
    ack_message =f"ACK for frames: {frames}"
    conn.send(ack_message.encode())
    
conn.close()
s.close()
```
### CLIENT.PY
```
import socket
s=socket.socket()
s.bind(('localhost',9999))
s.listen(1)
print("server listening...")
conn,addr=s.accept()
print(f"connected to {addr}")

while True:
    frames= conn.recv(1024).decode()
    if not frames:
        break
    
    print(f"received frames: {frames}")
    ack_message =f"ACK for frames: {frames}"
    conn.send(ack_message.encode())
    
conn.close()
s.close()
```

## OUPUT
### server.py
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/bcbf4c1f-50ab-4f01-9d86-cd8230ac1c3b" />
### client.py
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/b45b24ab-47b8-4d4f-b9a0-406ce57398b8" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
