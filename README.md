# EX-1.Echoserver
## Date:
Echo server and client using python socket
# AIM:
To develop a simple webserver to serve html programming pages.
# DESIGN STEPS:
## Step 1:
Design of echo server and client using python socket
## Step 2:
Implementation using Python code
## Step 3:
Testing the server and client 
# PROGRAM:
## SERVER CODE:
### echo-server.py
```
import socket

HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
## CLIENT CODE:
### Echo-client.py
```
import socket

HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")
```
# OUTPUT:
## SERVER CODE:

![1](https://github.com/Darkwebnew/Echoserver/assets/143114486/860388c7-ab37-4424-a17c-fb4f121cc0a1)

## CLIENT CODE:

![2](https://github.com/Darkwebnew/Echoserver/assets/143114486/c5c5619d-c1b9-4b41-a20a-a0bee4196267)

# RESULT:
The program is executed successfully
