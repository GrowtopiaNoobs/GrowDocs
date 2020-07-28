# Packet type 1

Packet senders:
- [ ] Client
- [x] Server


This packet is really simple. It contains always just one byte of data which is set to 0.

You want to send this packet always when client connects to server. Without this packet client won't send any login information nor any other packets.
