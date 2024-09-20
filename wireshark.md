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

1. It looks to be around 8 TCP connections because it takes a bit of back and forth for the server to return the hmtl and especially the images.
2. FRAME 4: 	0.025484815	192.168.186.128	172.233.221.124	HTTP	489	GET /index.html HTTP/1.1 
3. I can narrow it down to two frames (#222 and #224 for me) that are transporting a JPEG, but I cannot be sure which one corresponds to each image.

## ===== QUESTIONS =====

1. What is the signifigance of the server closing the connection vs the client?

