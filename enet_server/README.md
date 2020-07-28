# ENet server

Let's start with lowest level of everything. Growtopia is using networking library called ENet and this library works as wrapper around UDP connections. You will have to know only basics of ENet and you won't need to know UDP at all as ENet won't give you any access to it.

Now let's look at ENet, you will have to do basic configuration of it.
1. Use `enet_host_create` to create enet server. You probably want to set server to run at IP address `0.0.0.0`. This will make server aviable from all network interfaces you have. But you maybe also might want to use `127.0.0.1`, so it will bind server only to localhost and noone outside of your computer would be able to access it. Port which you choose can be anything you want, but you should keep in mind that if you choose port that have lower number than 1024, then you would probably have to run your server as administrator or root. Next thing is to choose number of clients you allow. You usually want to choose lowest possible number so all people can fit into your server. If you choose unreasonably high number, then you are vasting CPU cycles and memory. Now just couple last things. You need to specify number of channels. You should be fine with 1 channel as all Growtopia communication should be going on channel 0. Last thing is to choose limit for incoming and outcoming bandwidth. You should be here probably fine with 0 (this means unlimited bandwidth).
2. Set ENet checksum function to `enet_crc32`. This is required by Growtopia client and it won't connect without this (nor show any error).
3. Enable `enet_host_compress_with_range_coder` on your server. This is also required by Growtopia client and again it won't connect without this (nor show any error). Also it might be interesting to note that this piece of code compress Growtopia packets so they are smaller, but this makes them directly unreadable by network monitoring software like Wireshark.

Now you have it running! So let's look how to interact with Growtopia client.

You will be calling `enet_host_service` in loop to recieve new events.

There are basic three types of them:
1. `ENET_EVENT_TYPE_CONNECT` - This event is called when new peer connects.
2. `ENET_EVENT_TYPE_RECEIVE` - This event is called when there is new packet received.
3. `ENET_EVENT_TYPE_DISCONNECT` - This event is called when peer disconnects.

The only packet which carries data is recieve one. It's structure is not anyhow related with ENet, so here starts Growtopia packets part.

All Growtopia packets are made from two things:
1. Packet type - This is field with four bytes in size.
2. Packet data - This field have unlimited size, but always contain atleast one byte.

And here are those packet types:

1. [Packet type 1](packet_type1.md) - Login request packet
2. [Packet type 2](packet_type2.md) - ...
4. [Packet type 3](packet_type3.md) - ...
3. [Packet type 4](packet_type4.md) - ...
5. [Packet type 5](packet_type5.md) - ...
6. [Packet type 6](packet_type6.md) - ...

You will find there when to send those packets, then content and also table which tells you who is able of sending those packets (client or server).
