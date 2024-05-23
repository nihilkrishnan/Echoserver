## EXP 1
## NAME : NIHIL KK 
## REG NO : 212221223003

# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
Server Side:
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
Client Side:
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
## OUTPUT:
# SERVER OUPUT:
![Screenshot 2024-04-24 112220](https://github.com/Vinothini1711/Echoserver/assets/144300204/68bf7c88-8b52-49e1-9a0a-850666b814cb)
# CLIENT OUTPUT:
![Screenshot 2024-04-24 112200](https://github.com/Vinothini1711/Echoserver/assets/144300204/fcd4aaf5-8334-4a53-9d6b-b5450a886635)
## RESULT:
The program is executed successfully
