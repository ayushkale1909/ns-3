# ns-3
This is a network simulation script using the ns-3 network simulator. 

The code creates a point-to-point network between two nodes (node 0 and node 1) with a data rate of 5Mbps and a delay of 2ms. 

It sets up Internet stacks on the nodes and assigns them IP addresses in the subnet 10.1.1.0/24.

1. On node 1, a PacketSink application is installed which is set up to receive UDP packets on port 9. This is intended to act as a recipient for the data sent by node 0.
2. On node 0, a UdpEchoClient application is installed, which sends UDP packets to node 1. The client is configured to send 1 packet of size 1024 bytes with an interval of 1 second.
3. PCAP Tracing is enabled for all devices, and logging is enabled for the UdpEchoClient, UdpEchoServer, and PacketSink applications.

Results : 

At 2 seconds into the simulation, the UdpEchoClient on node 0 sent a 1024-byte packet to node 1, as confirmed by the log message and the pcap file for node 0.

At 2.00369 seconds into the simulation), the PacketSink application on node 1 received the 1024-byte packet from node 0, as confirmed by the log message and the pcap file for node 1. The delay is due to the 2ms delay configured for the point-to-point link.

Output on Terminal : 

At time +2s client sent 1024 bytes to 10.1.1.2 port 9

At time +2.00369s packet sink received 1024 bytes from 10.1.1.1 port 49153 total Rx 1024 bytes

