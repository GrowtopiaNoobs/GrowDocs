# Tank packet type 4

Packet senders:
- [ ] Client
- [x] Server

Fields used:
- [ ] NetID
- [x] Extended data


This packet is known as world packet. It contains all world blocks and their settings, dropped items and even weather settings and such stuff.

## Extended data description

- 6 bytes - currently unknown function
- string - world name
- uint32 - width in world blocks
- uint32 - height in world blocks
- uint32 - world size, which is simply multiplication of world width and height

From this moment starts array of block. Blocks are saved in left to right, followed by up to down order. All block data are placed one after another without any separator or anything.

### Tile data description

- uint16 - world foreground item id
- uint16 - world background item id
- uint16 - currently unknown data, it is recommended to keep them zero
- uint8 - first item flags
- uint8 - second item flags

Content of first item flags:
- 0x01 - ???
- 0x02 - ???
- 0x04 - ???
- 0x08 - ???
- 0x10 - ???
- 0x20 - Rotation of item (left/rigt)
- 0x40 - Enabled state of item
- 0x80 - Is item accesible by public

Content of second item flags:
- 0x01 - ???
- 0x02 - ???
- 0x04 - Water
- 0x08 - Glue
- 0x10 - Fire
- 0x20 - Red
- 0x40 - Green
- 0x80 - Blue

This data might by followed by extra tile data. There can be determined if there are any extra tile data by item id. This is done by checking item id in items data and getting it's action type. Item type then has to be translated into extra tile data type, which requires translation table and can't be sadly done by other way. Then if this type is other than 0, tile extra data are added.

You can read more about tile extra data more [here](extra_tile_data/README.md).

### Dropped items description

- uint32 - dropped items count
- uint32 - last dropped item uid

This is followed by data for each dropped item:

- uint16 - item id
- float - item x position (value is float type)
- float - item y position (value is float type)
- uint8 - item count
- uint8 - dropped item flags
- uint32 - item uid

Content of dropped item flags:
- 0x01 - Item shrinks when taken
- 0x02 - ???
- 0x04 - ???
- 0x08 - Radioactive item
- 0x10 - ???
- 0x20 - ???
- 0x40 - ???
- 0x80 - ???

### Last part of world data description

- uint16 - base weather
- uint16 - unknown data
- uint16 - current weather
- 6 bytes - unknown data
