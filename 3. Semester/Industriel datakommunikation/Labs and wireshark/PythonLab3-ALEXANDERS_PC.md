#### Code:
```Python
#import socket module

from socket import *

import sys # In order to terminate the program

  

serverSocket = socket(AF_INET, SOCK_STREAM)

#Prepare a sever socket

serverSocket.bind(('', 6789))

serverSocket.listen(1)

print('The server is ready to receive')

print('Ready to serve...')

  

#Establish the connection (just once)

connectionSocket, addr = serverSocket.accept()

try:

    message = connectionSocket.recv(1024).decode()

    filename = message.split()[1]

    f = open(filename[1:])

    outputdata = f.read()

  

    #Send one HTTP header line into socket

    connectionSocket.send("HTTP/1.1 200 OK\r\n".encode())

    connectionSocket.send("Content-Type: text/html\r\n".encode())

    connectionSocket.send("\r\n".encode())

    #Send the content of the requested file to the client

    for i in range(0, len(outputdata)):

        connectionSocket.send(outputdata[i].encode())

    connectionSocket.send("\r\n".encode())

  

    connectionSocket.close()

except IOError:

    #Send response message for file not found

    connectionSocket.send("HTTP/1.1 404 Not Found\r\n".encode())

    connectionSocket.send("Content-Type: text/html\r\n".encode())

    connectionSocket.send("\r\n".encode())

    connectionSocket.send("<html><body><h1>404 Not Found</h1></body></html>".encode())

    #Close connection socket

    connectionSocket.close()

  

serverSocket.close()

sys.exit()#Terminate the program after sending the corresponding data
```

![[Pasted image 20251020130831.png]]
![[Pasted image 20251020130906.png]]
