# TCP-opening-closing-in-C
TCP opening and closing process representation in C


Zaira E Cruz
CSCE 3530
November 9,2016

Compilation:
		gcc pserver.c -o pserver
		gcc client.c -o client

Execution:
		./pserver <port>
		./client <port>

Program mimics the TCP opening 3 way handshaking. And also mimics the 4 way closing TCP protocol.
Client first contacts the sender by sending a packet with an initial sequence number the SYN bit to 1. 
Then sender responds with an ACK packet with SYN and ACK bit set to 1. The client ends the 3 way 
handshaking by sending one last packet with ACK bit set to 1. 
The 4 way closing protocol is started by the client again and the FIN bit is set to 1. The sender
then responds with another packet that ACK the previous packet (ACK to 1). The sender again responds
with last packet setting their FIN bit to 1. The client again finalizes the connection by sending last
packet with ACK bit set to 1.

Source for checksum and tcp segment structure Dr. Robin J Pottathuparambil

In total:
		client: 
			sends 4 packets
			receives 3 packets

		sender: 
			sends 3 packets
			receives 4 packets 
