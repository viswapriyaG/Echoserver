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
### SERVER CODE: echo-server.py:
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
### CLIENT CODE: echo-client.py:
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
### SERVER OUTPUT:
![server output](https://github.com/viswapriyaG/Echoserver/assets/131427787/0c6bee74-e8e7-4ba9-b4ac-fd5c44326904)


### CLIENT SIDE:
![client output](https://github.com/viswapriyaG/Echoserver/assets/131427787/89fed7a6-bb7d-48be-81e1-70e27c257cf9)



## RESULT:
The program is executed successfully
