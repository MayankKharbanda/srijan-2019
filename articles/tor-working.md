# How TOR works?

---

| Question ? | Answer !                                                              |
| ---------- | --------------------------------------------------------------------- |
| writer     | Abhinav - MSc 1st year                                                |
| editor     | Shruti Katyal                                                         |
| Status     | Reviewed.                                   |
| Content    | Working of TOR                                                        |
| Plagiarism | None. 100% Unique. [Report Link](./plag-reports/plag-air-taxi-v1.pdf) |
| Verdict    | Aid to DarkWeb                                                        |

---

# How does TOR work?

Before we jump into its working, let us know what exactly is TOR. It's an open source browser that is used to surf the web but here's the catch, it does all this anonymously. 

TOR(The onion router) browser uses the concept of onion routing which was developed by the US Navy and it’s quite different from virtual private networks. What it basically does is that it bounces the connection between multiple routers so that it becomes very hard to track and can provide anonymity easily. Onion routing comes out as our savior because sometimes we don’t even want people to know that we have accessed something! While most of the communication we do is more or less based on client-server architecture, tor provides us the ability to stay completely anonymous. 

Now, let's see how do these bounces or hops work. The onion routing bounces the connection multiple times with encryption between each hop with different keys from the sender(tor user) to receiver(the server), and the last node on the path of hops actually communicates with the server(kind of a level one proxy) on behalf of the tor user. It seems that it is communicating with an intermediate node which is nothing but a tor client, just to confuse people about what’s going on the route from one end to another end.

The beauty of onion routing is that on the network no-one knows anything about the connection path, from where the packet came and where it was sent. Also, it uses asymmetric encryption techniques like AES, and keys with each node are K1, K2, K3 exchanged using Diffie Hellman algorithm. Just as there are layers in onion, here each layer has an encryption key. The message sent from the tor client is encrypted thrice with K1, K2, K3. Entry guard can peel the layer 1 with Key K1, and middle node can peel the encryption layer with K2 and so on, the data bus at the last _Exit_ relay that the message is not encrypted anymore because it is nothing but a request for something to the server, therefore, it must not be encrypted. Then the destination (the server) replies to the message and the reverse process happens from K3 to K2 to K1 and the response can only be opened from the Tor client from which the original request came because it has the key K1.

There can be hundreds of nodes between the ends each can be in different countries also. But the main point is that on each node, the exit and tor client both must be using SSL because the only part that is not encrypted is that part only.

With all this encryption going on this browser is definitely not the fastest! But it does what it’s designed to do, to make you anonymous and it does it pretty well!
