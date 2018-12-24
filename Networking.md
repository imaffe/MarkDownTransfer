## Networking

#### packet switches

calculate the chain delay with N routers

- queue delays and packet loss
- forwarding table and routing protocols
- circuit switching : reserve resource between two end systems
- IGNORE : details of two switches
- networks of networks
  - Points of Presence, multi-homing, peering, Internet exchange points
  - access ISP : bottom level ISP
  - content provider networks
- delay, loos and throughput in packet-switch networks
  - processing delays : microseconds
  - queue delay : micro to milli
  - transmission
  - propagation
- IGNORE: details of the delays
- IGNORE : packet loss and all remaining part in delay and loss

#### protocol layers and service models

- how to understand the 5 protocol layers
  - pass
- OSI model
- network security
- IGNORE : history of computer networking 

#### application layer

- c/s , b/s, p2p architecture 
- definition of client and server (differentb)
- four considerations choosing transport level protocol !
- TCP : offer congestion-control mechanism
- timing and through put can be satisfied using implementation.
- application-layer protocol defines how they passage message to each other ! 
- Web and HTTP
  - Non-persistent and persistent connections
  - Message Formats
  - Cookies
  - IGNORE : delay calculation of caching 
  - CDN : content distribution networks
  - Conditional GET
- FTP
- SMTP
  - sime details of SMTP
  - POP3 : email access protocals : no cross session state saved 
- DNS : Internet's Directory Service : UDP using port  53
  - so basically all daily hosts has DNS client !
  - QUES : what is canonical hostname ? hostname createed according to rules！ like standard name !
  - 3 main function : most important to me : load distribution
  - EXTRA : read the other operation on DNS on page 133
  - DNS caching : hierarchy DNS server 
    - recursive and iterative
  - DNS record and messages
- P2P
  - BitTorrent Protocols
  - IGNORE:  compare c/s and p2p scalability
  - IGNORE : DHT detail of the last 2 points

## Questions

- routers
- switches
- what is the process in traceroute.org means : there is a traceroute command in Linux
- what is the difference betweeen TCP SSL and HTTPS 
- what is RFC
- so many HTTP requests using port 80 ? won't it be filled with tremendous ones? 
- Does TCP must use socket ? 
- what is carriage return and line feed ?
- How to use telnet
- How do i know if I'm behind a proxy or not ? Who provides this proxy server ? What is difference of this between mirror ?	 
  - Like university and AOL:
  -  what is AOL? a company name !
- How does China prevent domestic user to ? How VPN solves this ?
- explain apache after this chapter ?
- who controls the conditional GET ? or what software on proxy provide this service ?
- does most linux distribution implement FTP on port 20 and 21?
- what is 7-bit ascii format ?
- does all TCP use the same handshaking patterns ? wh y there is initial SMTP handshaking? application layer handshaking ! 
- how can i interract with a mail server using telnet ! 
- what is MX record ? why web server and mail server can both be called enterprise.com
- why DNS use UDP ? any historical considerations ?
- How to know my local DNS server 
- How do i guarantee that the server is authorized host for a domain ?  only the bit ? cannot forge one?
- how to use nslookup program
- registrar usi TLD server ?
- what does Cloudfare do in this point of view !
