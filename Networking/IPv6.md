Topic: IPv6 Addressing Formats

What is IPv6?
- IPv6 is the new version of IPv4.
- It has a length of 128 bits providing much larger amount for devices to have an IP.

Why the need for IPv6?
- This is to provide solution to the depletion of IPv4 address.
- IPv4 may have run out of address as billions of devices now are connected to the Internet.  

IPv6 Addressing:
- 128 bit address using hexadecimal format with 8 hextets(16 bits) separated by colon.
- 2001:0DB8:85A3:0000:0000:8A2E:0370:7334

Dual Stack:
- Coexistence of both IPv4 and IPv6 in a device.

IPv6 Formatting Rules
- Help to reduce notation on IPv6 addresses.
- Rule 1: Omit Leading Zeroes
  - Omit leading zeroes on every hextet. Only leading not Trailing. ex. 01af -> 1af, 0000 -> 0
  - 2001 : 0db8 : 000a : 0001 : c012 : 9aff : fe9a: 19ac -> 2001 : db8 : a : 1 : c012 : 9aff : fe9a : 19ac
- Rule 2: Double colon
  - double colon can replace any single, contigous string of one or more hextets consisting all zeros. 2001:0000:0000 -> 2001::
  - 0000 : 0000 : 0000 : 0000 : 0000 : 0000 : 0000: 0001 -> ::1
