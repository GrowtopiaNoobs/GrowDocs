# OnSpawn

- [ ] requires netID set

Arguments:
- string - Spawn data

An example of spawn data:
```
spawn|avatar
colrect|0|0|20|30
posXY|0|0
name|Some user
country|ua
netID|1
userID|99743
invis|0
mstate|0
smstate|0
type|local
```

Explanation of these fields:
- `netID`: The NetID of the user. Used by other game packets.
- `userID`: The account ID of the user. (for example, an ID of 140 means this is the 140th GrowID created)
- `country`: The two letter country code that the player is from. `us` = United States, `id` = Indonesia, `jp` = Japan.
- `name`: The name of the user.
- `posXY`: The position of the user, in pixels
- `colrect`: The width (20) and height (30) of the bounding box of the player. Used for collision.
- `invis`: The invisibility status of the player. If invisible, doesn't render.
- `mstate`: If the player is a mod, this is bigger than zero. Can see invisible players that don't have an smstate set.
- `smstate`: If the player is a developer, this is bigger than zero. Can see all invisible players' faces.
- `type`: Whether the player is controlled by the peer or not. Leave it out entirely if this is a player that isn't controlled by the user.

