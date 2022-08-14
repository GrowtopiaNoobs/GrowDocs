# Items dat

This is special file, which is used for getting items names, texture files and coordinates, behavior and other stuff. It is also useful to know as it is used in multiple packets.

It is possible to first decoded items database on [this page](https://wombat.platymuus.com/growtopia/itemdb.php). Also based on this page was first [items dat decoder](https://github.com/GrowtopiaNoobs/Growtopia_ItemsDecoder) created.

## Items data structure

This structure begins with information about file and then this is followed by adding all items one after another.

Beginning structure:

uint16 for file version - this is updated when new fields are added
uint32 for item count

This is followed by all those items, items structure are following:

- uint32 - Item ID, starting from zero
- uint16 - Flags, such as untradable, world locked, public, foreground
- uint8 - Type, like 17 (foreground), or 20 (clothing)
- uint8 - Material (0 to 3)
- string - Item name, it is [encoded using simple cypher](cypher.md)
- string - Texture file name, used to load the item's sprite
- uint32 - Texture hash, used to check if the item's sprite is up to date
- uint8 - Visual effect (25 makes it rainbow like the Shifty Block)
- uint8 - Texture X - The X coordinate of the sprite in the sprite sheet, in multiples of 32
- uint8 - Texture Y - The Y coordinate of the sprite in the sprite sheet, in multiples of 32
- uint8 - Render Type - The render type of the sprite (0 - single sprite, 1 - spread like dirt)
- uint8 - Unknown byte, we don't know what it's used for
- uint8 - Collision type - (0 - no collision, 1 - full collision)
- uint8 - Block health (how many damage points it takes to fully destroy the tile, a punch normally delivers 6)
- uint32 - Another unknown field
- uint8 - Clothing type (7 - hair, 1 - shirt)
- uint16 - Rarity
- uint8 - Max items (200 usually, 2 on the Growtorial Entrance)
- string - Extra file name (usually used for audio, by default an empty string)
- uint32 - Extra file hash (to check if the extra file is up to date)
- uint16 - Animation length (in milliseconds)
- string - Unknown
- string - Unknown
- string - Unknown
- string - Unknown
- uint8 - Seed base sprite
- uint8 - Seed overlay sprite
- uint8 - Tree base sprite
- uint8 - Tree overlay sprite
- uint32 - Base color
- uint32 - Overlay color
- uint32 - Unknown
- uint32 - Tree grow time
- ... TODO
