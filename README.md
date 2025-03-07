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

### echo-server.py:
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

### echo-client.py
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
### echo-server.py:
![{DF61AC03-D454-4C02-B2B1-2B67BC8AB1D1}](https://github.com/user-attachments/assets/09fd4cf8-e86f-4c49-bf08-fc3aeb3af8d8)



### echo-client.py

![{96A58B57-964B-4F34-8BB1-B98A07A9D80C}](https://github.com/user-attachments/assets/84fc6bc4-a669-410f-be7a-0f6375fa98aa)




## RESULT:
The program is executed successfully.
