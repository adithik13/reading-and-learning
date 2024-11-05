let's dig into networking. 

https://beej.us/guide/bgnet/html/

linux seems to be the main go to for working with networking / sockets. people seem to drag their feet a bit when it comes to working with windows. thank god for OS. reptilian is coming in incredibly clutch here.

### What is a socket?

Sockets are essentially a way to speak to other programs using Unix file descriptors. 

A file descriptor is simply an integer associated with an open file. That file can be a network connection, a FIFO, a pipe, terminal, etc. *everything in Unix is a file*.

To actually get this file descriptor, we make a **Socket()** system call, which will then return the socket descriptor, and we can use it to communicate by using **send()** and **recv()** socket calls. 

Additionally, since it's a file (like everything else in Unix), we can use read() and write() commands too, but send() and recv() are stated to offer much more control over data transmission 

There are two main types of sockets: 
1. Stream Sockets (SOCK_STREAM)
	1. reliable, two-way connected communications streams. 
	2. very error free. 
	3. used by telnet and ssh applications, as well as HTTP
	4. stream sockets achieve this level of data transmission quality and reliability through [[TCP]], which ensures sequential and safe arrival of your data. like a seatbelt. maybe.
2. Datagram Sockets (SOCK_DGRAM)
	1. datagram sockets also use IP for routing, but they don't use TCP. Instead, they opt for [[UDP]].
	2. they are connectionless, because we don't have to maintain an open connection the way we would need to with stream sockets. 
	3. these are generally used when a TCP stack is unavailable or when a few dropped packets is not life ending 
	4. If you send a datagram, it may arrive. It may be out of order. But, it will be error free. 


TCP/IP is usually compared to OSI/ ISO model. This is the Layered Network Model and super popular. Layers of this model include: 

1. Application - where users interact with the network
2. Presentation
3. Session 
4. Transport
5. Network
6. Data Link
7. Physical - hardware: serial, ethernet etc 



### IP addresses, structs, data munging



