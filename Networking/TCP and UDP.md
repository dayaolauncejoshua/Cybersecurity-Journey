Topic: TCP and UDP (Transport Layer Protocols)

What is Transmission Control Protocol?
- TCP is a connection oriented protocol that ensures data is delivered reliably, in right order, and without errors/loss.
- HTTP/HTTPS, FTP, SMTP are some of known services that uses TCP connection

What is User Datagram Protocol?
- UDP is a connectionless protocol that sends data without guaranteeing delivery, order, or error recovery. Unreliable delivery.
- Video conference, playing mobile/video games, live streaming are examples of services that use UDP.
- It prioritize speed, It does check if every packets arrive.

- Both protocol works on the Layer 4 (Transport Layer)

Port
- Port is a logical endpoint that identifies a specific application or service on a device.
- TCP and UDP port numbers gets the data to the correct application or service

Why it matters in security:
- Port are common targets for attackers
- Port scanning (using tools like Nmap) discovers which services are running.
- Firewalls allow or block traffic based on TCP/UDP port numbers.
- SOC analysts inspect ports to identify suspicious or unauthorized services