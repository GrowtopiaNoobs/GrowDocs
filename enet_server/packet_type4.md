# Packet type 4

Packet senders:
- [x] Client
- [x] Server

This is one of most complicated packets. Also this is one of few packets which have known official name, which is Tank Packet. It contains it's own packet type together with static structure and data with dynamic length which can be placed on end of packet. Also when there is choosen variant packet as packet type, then you can pack onto it another layer of data.

So let's look at packet structure first (it is always 56 bytes, not counting extended data):
- uint8 - Packet type
- uint8 - ...
- uint8 - ...
- uint8 - ...
- uint32 - NetID
- uint32 - ...
- uint32 - ...
- uint32 - ...
- uint32 - ...
- float - ...
- float - ...
- float - ...
- float - ...
- float - ...
- uint32 - ...
- uint32 - ...
- uint32 - Extended data length




Packet types:
- [00 - Character update state](tank_packets/type00.md)
- [01 - Variant packet](tank_packets/type01.md)
- [02 - ...](tank_packets/type02.md)
- [03 - ...](tank_packets/type03.md)
- [04 - World packet](tank_packets/type04.md)
- [05 - ...](tank_packets/type05.md)
- [06 - ...](tank_packets/type06.md)
- [07 - ...](tank_packets/type07.md)
- [08 - ...](tank_packets/type08.md)
- [09 - Inventory update packet](tank_packets/type09.md)
- [10 - ...](tank_packets/type10.md)
- [11 - ...](tank_packets/type11.md)
- [12 - ...](tank_packets/type12.md)
- [13 - ...](tank_packets/type13.md)
- [14 - ...](tank_packets/type14.md)
- [15 - ...](tank_packets/type15.md)
- [16 - Items data update](tank_packets/type16.md)
- [17 - ...](tank_packets/type17.md)
- [18 - ...](tank_packets/type18.md)
- [19 - ...](tank_packets/type19.md)
- [20 - ...](tank_packets/type20.md)
- [21 - ...](tank_packets/type21.md)
