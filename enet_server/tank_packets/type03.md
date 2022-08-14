# Tank packet type 3

Packet senders:
- [x] Client
- [x] Server

Fields used:
- [x] NetID
- [x] Offset 12
- [x] Main Value
- [x] Tile X/Y


This packet is known as the Set Tile packet. It requests a tile placement operation.

If the client receives the 'main value' of 18, the block is destroyed.

The player requests a punch on a tile by sending a "set tile" packet with the main value of 18, and wrenches with a main value of 32.

The Tile X/Y is used to determine what tile is being updated.

