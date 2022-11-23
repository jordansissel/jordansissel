# Projects

## [fpm](/jordansissel/fpm)

* Created: 2011. Actively maintained.
* Uses: Ruby

As a sysadmin, I've often needed to package internal software, repackage external software, etc. Depending on the operating system, I'd often need to use completely different tools to solve the same problem. This bothered me, so I wrote fpm.

fpm's job is to simplify the packaging process by giving you a single tool to create new packages, convert packages to other formats, repackaging existing things, and more, without requiring a large cognitive burden.

## [xboxproxy](/jordansissel/xboxproxy)

* Uses: C, libnet, libpcap
* Created: ~2005. Inactive.

During the college academic year, we would play Halo on the LAN quite a bit, but as folks graduated, it became more difficult to play together. 

Enter xboxproxy. This project allowed us to play local/LAN-networked games over great distances.

The way it worked was listening for local xbox discovery traffic which kind of ignores the IP layer and sets all IP addresses, source and destination, to `0.0.0.1`. Note, this was with the original Xbox which called this kind of local play, "system link". Discovery had the Xbox send a broadcast ethernet packet, and neighboring Xboxes would respond accordingly.

If we forwarded these packets over UDP to a remote system which replayed the packets on the local network? Boom. Xbox LAN games across long distance networks on different subnets.

The actual implementation uses pcap to capture packets, a hashmap(?) to keep track of which proxy IP addresses contained which Xboxes (mac address), and little else.

Later implementations captured multicast to permit iTunes audio forwarding, if I recall.
