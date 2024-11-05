1. explain the range of TCP/IP classes: 
	1. ![[Pasted image 20241105122100.png]]
2. What are Pvt. IP address?: 
	1. private IP address of a system is the IP address that is used to communicate **within the same network** 
3. does IP protect data on the network?
	1. IP doesn't guarantee correct delivery, and can potentially be out of order
	2. this method leaves the data protection to the transport protocol
	3. TCP and UDP, however, can guarantee that the data is correct upon delivery.
		1. much more secure
	4. using IP layer, the correct destination of the packet is identified and delivered
	5. the TCP / UDP then check if the data is correctly delivered with Checksum
		1. if destination IP is not alive, then the packet is hopped by decreasing the time to leave. 
		2. and the the packet is considered lost and undelivered
		3. if the transport 
4. what are some services provided by TCP?: 
	1. process to process communication
	2. stream orientation
	3. full duplex service
	4. multiplexing
	5. reliability
5. explain TCP protocol header format: 
	1. ![[Pasted image 20241105124718.png]]
6. name TCP flags: 
	1. URG: urgent pointer is valid
	2. ACK: Acknowledgment number is valid (in case of cumulative acknowledgement)
	3. PSH: request for a push 
	4. RST: reset the connection 
	5. SYN: synchronize sequence numbers
	6. FIN: terminate the connection
7. what is the role of TCP checksum?
	1. this is one of the important fields of TCP protocol format
	2. 16 bits long 
	3. holds the checksum error control
	4. mandatory in TCP, not in UDP
8. what is PORT?
	1. a physical docking point that is basically used to connect the external devices to the computer
	2. acts as an interface between the computer and the external devices
9. what are some well-known ports that TCP uses?: 
	1. echo: echos whatever is sent to it, TCP and UDP
	2. discard: discards any datagram that is received
	3. FTP: used by file transfer protocol to send data to clients, TCP
	4. telnet: used by telnet to remotely connect to a workstation or server (unsecured), TCP
	5. simple mail transfer protocol (SMTP): to send emails!, TCP
	6. Domain name system (DNS): for DNS requests, network routing, and zone transfers, TCP
	7. BOOTP: boostrap, TCP
	8. Hyper Text Transfer Protocol (HTTP): for webpages online, TCP
	9. Post Office Protocol(POP3): used to retrieve complete contents of a server mailbox, TCP 
10. what is "Endpoint" in TCP?: 
	1. TCPEndpoint allows you to easily establish and communicate over TCP/IP network connections between client and server processes, which may possibly reside on different hosts.
	2. follows a telephone-like model of networking
	3. clients can "Call" servers, and servers "answer"
	4. \once a connection is established, the client and server can "talk" to each other from reading and writing to the connection 
11. what is the error control mechanism in TCP?: 
	1. TCP protocool has methods of finding corrupted segments, missing segments, out of order segments, and duplicated segments
		1. mainly done through Checksum, Acknowledgement, and Retransmission
12. What is congestion?
	1. a state that occurs in the network layer when the message traffic is so heavy that it slows down network response time
13. what is the difference between stop and wait and sliding window?
	1. ![[Pasted image 20241105125848.png]]
14. what is round trip time?: 
	1. the length of time taken by a data packet to be sent to a destination
	2. includes the time it takes for an acknowledgement of that packet to be received back at the original place 
15. what is the significance of TCP acknowledgements? 
	1. used to acknowledge packets that are successfully received by the host
	2. a flag is set if the acknowledgement number field contains a valid acknowledgement number
16. What is retransmission?
	1. resending packets over the network that have either been lost or damaged
	2. retransmission protocols such as those provided by TCP can provide reliable communication 
17. what are features of TCP?: 
	1. connection-oriented: applications request a connection to be the destination which is used to transfer data
	2. stream data transfer: it is TCP's responsibility to pack this byte stream into packets, known as TCP segments. These segments are then passed to the IP later for transmission to the destination device
	3. reliable: it can recover data from the network layer if data is damaged, duplicated, or corrupted
	4. point-to-point: TCP connection provides end-to-end delivery 
	5. Interoperability: eliminates cross-platform boundaries
	6. error and flow control: error checking, flow control, and acknowledgement functions
	7. name resolution: helps in solving human-readable names into IP addresses 
	8. routability: TCP/IP is routable
	9. full duplex: can provide connection that goes both ways
18. what is SCTP protocol?
	1. a connection oriented protocol on computer networks that provides a full-duplex association, sch as transmitting multiple streams of data between two endpoints at the same time that have established connection in the network
	2. can be called next gen TCP or TCPng.
	3. makes it easier to support telephonic conversation on the internet
	4. makes it easier to establish a reliable connection 
	5. standard protocol
19. what is a three-way handshake protocol?
	1. step 1: SYN
		1. client wants to establish a connection with the server
		2. sends a segment with SYN which informs the server that the client is likely to start yapping
		3. tells what sequence number starts the segments
	2. step 2: SYN + ACK
		1. now the server responds to the client request with SYN-ACK bits set 
		2. ACK (acknowledgement) decides whether or not the response segment has been received 
		3. SYN = the number that segments will start with 
	3. step 3: ACK 
		1. the client acknowledges the response of the server and they both establish a reliable connection with which they will start data transfer
20. describe the difference between leaky bucket and token bucket: 
	1. ![[Pasted image 20241105131141.png]]
21. why is token bucket sometimes better than leaky bucket?
	1. if a bucket is full of tokens, tokens are discarded, not packets
	2. in a leaky bucket, packets are discarded
	3. token bucket can send larger bursts at a faster rate
22. what are TCP connections phases?
	1. connection establishment 
	2. data transfer 
	3. connection termination 
23. what are some features of TCP sliding window?
	1. uses variable size windows to provide flow control as well as reliable transfer
	2. TCP connections are full duplex
		1. both transfers to & fro proceed simultaneously over each connection, one in each direction 
	3. supports machines of various speeds and sizes and communicates through a network and routers of various speeds
24. what is the maximum / min size of the TCP header?
	1. max = 60 bytes
	2. min = 20 bytes
25. do port addresses need to be unique?
	1. port addressing is done by the transport layer
	2. the fourth layer of the OSI model
	3. port addresses are short because they have to perform end-to-end delivery of the message and protocols are less in number than computer systems
	4. port addresses are less than IP addresses
	5. IP address refers to the computer / devicce connected and the port address refers to a particular protocol to communicate with the server as per client request
26. are UDP and IP unreliable?
	1. no, UDP is unreliable and connectionless
	2. IP's unreliability lies in upper layer protocols
		1. IP packet becomes unreliable if the upper layer is TCP
	3. UDP is more reliable in terms of data integrity than IP 
	4. checksum in the IP header only applies to the header itself, not the whole packet 
	5. UDP checksum applies to the whole user segment
27. what is a datagram?
	1. a logical transfer unit to transfer information over the network
	2. the data is transmitted from source to destination 
	3. does not guarantee that data will be delivered or lost on the way 
	4. has two section headers and a data payload 
	5. travels in-network without any prior virtual network between source and destination 
	6. data is frequently divided into smaller parts and transmitted to the defined route
28. what are the registered port and dynamic port?
	1. registered port: ports 1024-49151, not assigned and controlled by an IANA, and can only be registered with IANA to prevent duplication 
	2. dynamic port: 49152 to 65535, neither controlled nor registered, can be used in any process
29. what is the importance of the TTL field?
	1. the lifespan of the data that's being sent
	2. after that specified time is over, the data will be discarded or can be stated as a number of hops that the packet is set to exist in the network, after which the packet is discarded
	3. TTL is meant to help avoid a situation where an undeliverable datagram keeps circulating in the network, floating around like a lost soul
30. 