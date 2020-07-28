# Types definiton

There are few basic types in packets used. Most of them are classica C types, but there are few small differences.

## string

This type is made of uint16, which specifies in bytes how long the string is and followed by the text itself.

## text

This is sequence of bytes.

## Other types

Other types are classical C types, but they are just missing `_t` suffix. Also there is usually prefix `u`, that means those values are unsigned. But this prefix can be often wrong as it is hard to correctly determine.
