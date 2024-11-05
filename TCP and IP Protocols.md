### What even is TCP / IP? 

The TCP / IP model is a fundamental framework for computer networking. 

TCP = Transmission Control Protocol
IP = Internet Protocol

This model defines how data is transmitted over network, ensuring reliable communication between devices. It consists of four main layers: 
1. Link Layer
2. Internet Layer
3. Transport Layer
4. Application Layer

TCP/IP was initially developed by the DoD in the 60's (shocker), and is based on standard protocols. Created alongside ARTPANET, the predecessor to modern internet, the lower level hardware details and physical transmission medium were largely abstracted away in favor of higher level [[networking]] protocols. 

It is a more concise version of the OSI model. (OSI has seven layers).

Can be broken into 2 actions: 
1. TCP provides reliable data delivery
2. IP handles addressing & routing packets over networks

The main purpose of TCP/IP is to transfer data from one computer to another. The main condition is to make this data reliable and accurate. The reader should have the same information every time. 

In order to ensure that the data in question reaches the destination safely, the TCP / IP model divides data into packets and combines them at the other end of transmission. 


![[Pasted image 20241101224627.png]]

### Layers of the TCP / IP Model: 

1. Network Access Layer
	1. this layer is a group of applications requiring network communications. This layer is responsible for generating the data itself and requesting connections. This acts on behalf of the sender. 
	2. The packet's network protocol type, here TCP/IP, is also identified by the network access layer.
	3. This layer also provides error prevention and framing
		1. framing and Ethernet IEEE 802.2 framing are two examples of data-link layer protocols
2. Internet or Network Layer: 
	1. this layer parallels the OSI's network layer. It defines the protocols which are responsible for the logical transmission of the data over the entire network. 
	2. the main protocols in this layer are as follows: 
		1. IP: Internet protocol
			1. responsible for delivering packets from the source host to the destination host by looking at IP addresses
			2. two versions, IPv4 and IPv6. IPv4 currently is more popular
		2. ICMP: Internet Control Message Protocol
			1. encapsulated within IP datagrams and responsible for providing hosts with information about network issues
		3. ARP: Address Resolution Protocol
			1. Responsible for finding the hardware address of a host from a known IP address. 
			2. has several types: Reverse ARP, Proxy ARP, Gratuitous ARP, & Inverse ARP
	3. the internet layer is responsible for routing packets of data from one device to another across a network
		1. this is done by assigning each device a unique IP address, which is used to identify the device and determine the route that packets should take to reach it
3. Transport Layer
	1. This layer's protocols exchange data receipt aknowledgements and retransmit missing packets to ensure that packets arrive in order & without any errors. 
	2. This is end to end communication 
	3. two protocols in this layer are: 
		1. [[TCP]]: Transmission Control Protocol, transmits data in a way that resembles char-by-char transmission rather than separate packets. 
			1. one starting point initially establishes the connection, and then the whole transmission continues in byte order, and the ending byte closes the connection
		2. [[UDP]]: User Datagram Protocol, a service that provides datagram delivery. Connections between receiving and sending hosts are not verified by UDP. Usually used by applications that transport only small amounts of data rather than TCP, because it eliminates the processes of establishing and validating connections
	4. Application Layer
		1. This is analogous to the transport layer of the OSI model. It deals with end-to-end communication and error-free data delivery. This also shields the upper layer applications from data complexity. 
		2. there are three main protocols in this layer: 
			1. HTTP and HTTPS: 
				1. HTTP = Hypertext transfer protocol. used by the world wide web and manages communication between browsers and servers. 
				2. HTTPS: HTTP-Secure, and is a combination of HTTP with SSL(Secure Socket Layer), and is efficient in cases where the browser needs to fill out forms, sign in, authenticate, and carry out bank transactions (anything personal, private, or sensitive with a lot of back and forth)
			2. SSH: Secure Shell.  A terminal emulations software like Telnet. This creates a secure session over TCP/IP connection. 
			3. NTP: Network Time Protocol, this synchronizes clocks between our computers and one standard time source. Crucial for more sensitive things like bank transactions
		3. This is similar to the host-to-host layer in the OSI model. This is responsible for: 
			1. Reliable Data Transfer
			2. Segmentation & Reassembly 
			3. Multiplexing & Demultiplexing
			4. End-To-End Communication


### Why doesn't TCP/IP have a physical layer?

A physical layer isn't employed by TCP/IP model because the data link layer is considered the point at which the interface occurs between TCP / IP stock and the underlying network hardware. TCP/IP is designed to be independent of underlying network hardware. This is what makes TCP/IP so alluring, its flexibility as compared to older models. 


### Advantages of TCP/IP Model: 
1. Interoperability: 
	1. allows different types of computers and networks to communicate 
	2. promotes compatibility in diverse systems
2. Scalability: 
	1. super scalable tbh
3. Standardization:
	1. based on open standards and protocols, so different devices can collaborate without compatibility issues 
4. Flexibility:
	1. supports different kinds of routing protocols, data types, and communication methods, which makes it adaptable to different networking needs
5. Reliability:
	1. includes error-checking and retransmission features in case something happens, which ensures reliable data transfer. 


### Disadvantages of TCP/IP: 
1. Complex Configuration:
	1. setting up and managing can be complicated, especially for networks with many devices
	2. can sometimes lead to configuration errors
2. Security Concerns: 
	1. TCP/IP was not designed with security in mind tbh
	2. sometimes can have some vulnerabilities
3. Inefficient for Smaller Networks: 
	1. not really necessary for small networks
4. Limited Address Space: 
	1. IPv6 addresses this issue, but IPv4 still has a limited address space, which can lead to address exhaustion in larger networks
5. Data Overhead:
	1. TCP requires a lot of overhead to ensure reliable transmission. This can reduce efficiency. 


To practice with these concepts, we can also explore some [[TCP/IP interview questions ]]