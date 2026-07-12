Topic: Dynamic Host Configuration Protocol (DHCP)

What is DHCP?
- It is a protocol that automatically assigns address information, and other configuration on a device connected in a network.

How does DHCP Work?
- A connecting device sends out a DHCP Discover, which sends a packet containing its MAC address and finds a DHCP server.
- DHCP responds with a DHCP Offer, containing an IP address and configuration which the host/device could use if it accepts it.
- Once the device receives the DHCP Offer packet, the device then sends a DHCP Request, that it will accept the offer.
- After the DHCP server receives the request, the server then sends a DHCP Acknowledgement that will indicate that the device will use the IP address information and configuration associated with its MAC Address.