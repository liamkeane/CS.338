## Liam Keane
## Wireshark introduction assignment

## ===== DAYTIME =====

1. Identify the parts of the TCP 3-way handshake by listing the frame summaries of the relevant frames.
FRAME 1: 	0.000000000	10.133.6.241	129.6.15.28	TCP	74	53804 → 13 [SYN] Seq=0 Win=32120 Len=0 MSS=1460 SACK_PERM TSval=3546105462 TSecr=0 WS=128
FRAME 2:	0.050792538	129.6.15.28	10.133.6.241	TCP	66	13 → 53804 [SYN, ACK] Seq=0 Ack=1 Win=65535 Len=0 MSS=1382 WS=64 SACK_PERM
FRAME 3: 	0.050844295	10.133.6.241	129.6.15.28	TCP	54	53804 → 13 [ACK] Seq=1 Ack=1 Win=32128 Len=0
2. 53804
3. When the server sends its reponse the computer needs to know which process to deliver the message (indicated by an integer).
4. FRAME 4:	0.066628293	129.6.15.28	10.133.6.241	DAYTIME	105	DAYTIME Response
5. Syncronization and Acknowledgment
6. The server initiated the closing because they sent the first [FIN] message.

## ===== HTTP =====
Despite my best efforts, I was not able to capture any packets when filtering and connecting to the website. 
1. How many TCP connections were opened? How can you tell?
2. Can you tell where my homepage (index.html) was requested? (If not, why not? If so, include frame summaries and/or other info that supports your answer.)
3. Can you tell where my photograph (jeff-square-colorado.jpg) was requested? (If not, why not? If so, include frame summaries and/or other info that supports your answer.)

## ===== QUESTIONS =====

1. What is the signifigance of the server closing the connection vs the client?

