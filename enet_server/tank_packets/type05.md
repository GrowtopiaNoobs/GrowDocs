# Tank packet type 4

Packet senders:
- [ ] Client
- [x] Server

Fields used:
- [ ] NetID
- [x] Tile X/Y
- [x] Extended data


This packet is known as update tile packet. It contains one world block's data.

The Tile X/Y is used to determine what tile is being updated.

## Extended data description

The extended data contains one block's data, as if it were part of the world data packet.

Check [the tile data description](type04.md#tile-data-description) for more info.

