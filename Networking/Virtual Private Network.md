**Virtual Private Network**
    - a technology that creates a secure tunnel or connection between devices or networks over public networks, such as the Internet.
    - the Internet can deliver packets from one location to another, but a normal network communication does not automatically guarantee that all traffic is protected from being read or altered.
    - Without VPN:
        Branch Office ───── Internet ───── Main Office
    - With VPN:
        Branch Office ═══ Encrypted Tunnel ═══ Main Office
                            Internet
    - Once you connect to a VPN, your traffic first goes to the VPN server before going to its final destination.
        - Eg. Security testing server located in other country and you're in Philippines. With a VPN connection, the security testing server sees the Japanese VPN server's IP address instead of your Philippine public IP.
        - The VPN acts as a middle server. Your traffic goes through it, and the destination sees the VPN server's IP address.

**VPN Routing and IP Leaks**
    1. Not all VPNs route all your Internet traffic
        - Some VPNs are configured only to give you access to a private network. Eg. a company VPN -- only traffic intended for the company network goes through the VPN. Your normal Internet traffic still goes through your ISP.
    2. VPN IP leaks
        - Sometimes a VPN is expected to hide your real public IP, but information can accidentally bypass the VPN.
        - One possible issue is a DNS leak, where your DNS requests do not go through the VPN as expected. This can reveal information about your network activity to your normal DNS provider or ISP.

**Key**
    - A VPN does not always mean that all traffic automatically goes through the encrypted tunnel.
    - It depends on the VPN configuration:
        1. Full Tunnel:
            All Traffic → VPN → Internet
        2. Split Tunnel:
            Private/Company Traffic → VPN
            Other Internet Traffic → ISP
    - So, depending on why you use a VPN, you may need to check for issues such as IP leaks or DNS leaks.