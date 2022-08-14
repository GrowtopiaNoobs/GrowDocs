# Type definitions

There are few basic types used in packets. Most of them are classic C types.

## `string`

This type is encoded as a uint16, followed by the bytes that make up the text.

Example: `05 00 48 65 6c 6c 6f` would be deserialized into "Hello".

## `int8` and `uint8`

This is a plain old byte. There's nothing special about it. `int8` is rare to see.

Example: `64` = 0x64 = 100

## `int16` and `uint16`

This is an integer that can store between 0 and 65536 (or -32768 and 32767 in the case of signed int16). It is encoded in little-endian format.

Example: `01 00` = 1 (uint16). `00 01` = 0x100 = 256 (uint16). `FF 80` = 0x80FF = 33023 (uint16) or -32513 (int16)

## `int32` and `uint32`

This is a 32-bit integer that can store values between 0 and 4.294.967.295 (or -2.147.483.648 to 2.147.483.647 in the case of a signed int32). It is also encoded in little-endian format.

Example: `00 00 01 00` = `0x00010000` = 65536.

