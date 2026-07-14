Topic: Address Resolution Protocol

Two Primary Addresses:
- Physical Address (MAC Address) - Used for NIC to NIC communication on the same Ethernet Network (Layer 2)
- Logical Address (IP Address) - Used to send packet from source device to destination device. Source IP address can be on the same network or not with the destination IP address.

What is ARP
- ARP is a protocol that works on Layer 2. It finds the MAC address of a device on the same network who's its IP address is already known.
- If the host doesn't know which one has this IP address or it is not in its ARP table, it sends an Ethernet broadcast or ARP Request to all devices on the same network to determine its MAC address.
- The device that matches the IP address on the frame from ARP request will reply (ARP Reply) with its MAC Address
- The hosting device will then register the IP and MAC address in the ARP table then proceeds to send packet to the destination device