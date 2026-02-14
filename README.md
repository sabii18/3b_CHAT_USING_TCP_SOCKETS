# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM

### Server:
~~~
import socket

s=socket.socket()

s.bind(('localhost',12345))

s.listen(1)

c,addr=s.accept()
print("Connection Established")
while True:

    msg=c.recv(1024).decode()
    print("Client:",msg)

    c.send(input("Server: ").encode())

    if msg == "bye":
        break


s.close()
~~~

### Client:
~~~
import socket

c=socket.socket()

c.connect(('localhost',12345))

while True:

    c.send(input("Client: ").encode())

    msg = c.recv(1024).decode()

    print("Server:",msg)

    if msg == "bye":
        break


c.close()
~~~
## OUPUT

<img width="1919" height="1019" alt="Screenshot 2026-02-14 113854" src="https://github.com/user-attachments/assets/cf9c57f1-96e8-429a-973a-df506a093699" />


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
