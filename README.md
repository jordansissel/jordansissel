# Projects

## [xboxproxy](/jordansissel/xboxproxy)

Uses: C, libnet, libpcap

During the college academic year, we would play Halo on the LAN quite a bit, but as folks graduated, it became more difficult to play together.

Enter xboxproxy. This project allowed us to play local/LAN-networked games over great distances.

The way it worked was listening for local xbox discovery traffic which kind of ignores the IP layer and sets all IP addresses, source and destination, to `0.0.0.1`. Note, this was with the original Xbox.
Discovery had the Xbox send a broadcast ethernet packet, and neighboring Xboxes would respond accordingly.

If we forwarded these packets over UDP to a remote system which replayed the packets on the local network? Boom. Xbox LAN games across long distance networks on different subnets.

The actual implementation uses pcap to capture packets, a hashmap(?) to keep track of which proxy IP addresses contained which Xboxes (mac address), and little else.

Later implementations captured multicast to permit iTunes audio forwarding, if I recall.
