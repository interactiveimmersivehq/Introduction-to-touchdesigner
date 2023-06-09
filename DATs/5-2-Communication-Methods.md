
### *5.2 Communication Methods*

There are quite a few DATs that are capable of providing inputs and outputs over the many standard communication protocols. TouchDesigner is able to communicate natively over MIDI, OSC, TCP, UDP, UDT, and Websocket, giving it the ability to speak to many different types of programs, web applications and services, show control hardware, other computer systems, and etc.

MIDI, OSC, and DMX protocols were explained in the CHOP chapter. DATs can communicate over the same protocols, and quite a few more.

TCP is the internet standard communication protocol. It is a connection oriented protocol, meaning there is a clear client-server relationship between the communicating parties, and a connection must be established (usually behind the scenes) before any data is transmitted. This relationship allows TCP connections to be reliable, in that the communicating parties can provide acknowledgment of all data sent and received, meaning no data ever gets lost. TCP is an ordered delivery stream, meaning data sent in a specific order, will be received in that same order.

UDP, on the contrary, is a connection-less protocol, in that no explicit connection is established prior to data transmission. This creates a level of unreliability in areas such as delivery acknowledgments, dropped packets, and order of messages. If none of these are crucial to a project, there are some performance gains in systems where dropped packets are less of an issue than delayed packets. 

UDT is one of the newer communication protocols. It is essentially the better parts of UDP and TCP combined. It is built on the UDP protocol, but is connection-based, and reliable. This means that is has the same acknowledgments and data ordering that a TCP connection would have, but over the faster UDP protocol.

A benefit of connection-less protocols is that they support a feature called 'Multicast messaging'. This means that regardless of how many computers are connected, each message is only sent over the network once. When sending the same message to many computers, this removes the overhead of sending the same message to each individual computer. This is the opposite of 'Unicast messaging', in which each connected computer receives an individual message, even if the message being sent to every machine is the same.

Websocket is the go-to communication method when working with web browsers and real-time web applications. It has been designed from the ground up to be used as an interface between web browsers and servers, and the protocol has simplified some key functionality in regards to bi-directional web communication. 

{pagebreak}
