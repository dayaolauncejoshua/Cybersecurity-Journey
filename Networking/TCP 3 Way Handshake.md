**TCP Three Way Handshake**

**User Datagram Protocol**
    - A fast and connectionless protocol. It doesn't need to establish a connection and doesn't guarantee that a packet is delivered. It is suitable on fast queries such as DNS and for real-time communications such as audio/video calling, live streaming, gaming, etc.

**Transmission Control Protocol**
    - A connection-oriented protocol. It ensures that data is delivered accurately, reliably, and on the right order. It requires to establish a TCP connection before data is exchanged.
    - A TCP connection is established using three-way handshake.
        - Two flags: SYN (Synchronize) and ACK (Acknowledgement)
        - Three steps of establishing TCP connection:
            1. SYN - client initiates the connection by sending a SYN packet to the server. "Can we connect?"
            2. SYN-ACK - the server responds with a SYN-ACK. That means that the server want to synchronize also the connection and it acknowledges that it receives the client's request. "Yes, I acknowledge your request."
            3. ACK - the client acknowledges the SYN-ACK. This completes the establishment of the connection.