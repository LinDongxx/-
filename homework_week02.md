#### p6.

a）

Either the client or the server can indicate to the other that it is going to close the persistent connection. The reason is that we  include the connection-token  "close" in the Connection-header field of the http request/reply.

b) None 

c) according to RFC2616 “Clients that use persistent connections should limit the number of  simultaneous connections that they maintain to a given server. A single-user client  SHOULD NOT maintain more than 2 connections with any server or proxy.”

d) yes ,according to RFC2616 “A client might have started to send a new request at the same  time that the server has decided to close the "idle" connection. From the server's point  of view, the connection is being closed while it was idle, but from the client's point of  view, a request is in progress.”

p12



`Server.py`

`from socket import *` 

`serverPort=12000` 

`serverSocket=socket(AF_INET,SOCK_STREAM)`

 `serverSocket.bind(('',serverPort))` 

`serverSocket.listen(1)` 

`connectionSocket, addr = serverSocket.accept()` 

`while 1:` 

`sentence = connectionSocket.recv(1024)`

 `print  'From   Server:',   sentence,  '\n'`  

`serverSocket.close()`

