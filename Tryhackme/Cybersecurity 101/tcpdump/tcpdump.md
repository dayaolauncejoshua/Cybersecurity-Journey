**What is tcpdump?**
    - is a command-line packet capture tool. It captures and displays network traffic directly from the terminal.

**Example commands**
1. tcpdump -i INTERFACE - Captures packets on a specific network interface
2. tcpdump -w FILE - Writes captured packets to a file
3. tcpdump -r FILE - Reads captured packets from a file
4. tcpdump -c COUNT - Captures a specific number of packets
5. tcpdump -n - Don’t resolve IP addresses
6. tcpdump -nn - Don’t resolve IP addresses and don’t resolve protocol numbers
7. tcpdump -v - Verbose display; verbosity can be increased with -vv and -vvv
    * tcpdump -i eth0 -c 50 -v captures and displays 50 packets by listening on the eth0 interface, which is a wired Ethernet, and displays them verbosely.
    * tcpdump -i wlo1 -w data.pcap captures packets by listening on the wlo1 interface (the WiFi interface) and writes the packets to data.pcap. It will continue till the user interrupts the capture by pressing CTRL-C.
    * tcpdump -i any -nn captures packets on all interfaces and displays them on screen without domain name or protocol resolution.