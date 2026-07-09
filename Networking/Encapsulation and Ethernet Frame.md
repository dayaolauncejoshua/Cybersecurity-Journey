Topic: Encapsulation and the Ethernet Frame

Encapsulation
What I learned:
- It is a process of placing one message format inside another message format
- Wrapping data with additional information (headers and sometimes trailers) as it moves down the network layers before being sent across a network.

Why it matters in Cybersecurity:
- It helps inspect network traffic and detect attacks
Examples:
  - Wireshark lets analysts inspect the headers added during encapsulation to see IP addresses, ports, protocols, and other details.
  - Firewalls examine encapsulated packet information (such as IP addresses and ports) to decide whether to allow or block traffic.
  - During incident response, analysts trace malicious traffic by examining the headers added at each layer.

Without encapsulation, devices wouldn't know:
  - Where data should go.
  - Which application should receive it.
  - How to deliver it correctly.

Ethernet Frame
What I learned:
  - format used to send data over a wired Ethernet network. It encapsulates the packet from the Network layer by adding information needed to deliver it across the local network.
  - It is like an envelope that carries an IP packet from one device to another on the same LAN.
  - Ethernet Frame Fields:
    - Preamble = Synchronizes the sender and receiver so they know a frame is about to arrive.
    - Destination MAC Address = The MAC address of the device that should receive the frame.
    - Source MAC Address = The MAC address of the sender.
    - EtherType (Type) = Identifies what type of data is inside (e.g., IPv4, IPv6, ARP).
    - Data (Payload) = The actual data being sent, usually an IP packet.
    - Frame Check Sequence (FCS) = Detects errors during transmission using a CRC (Cyclic Redundancy Check).

Why is it Important in Cybersecurity:
  - Since it works on Layer 2, this identifies the source and destination devices using MAC addresses
  - Detect ARP spoofing and other Layer 2 attacks.
