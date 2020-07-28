# Tank packet type 1

Packet senders:
- [ ] Client
- [x] Server

Fields used:
- [x] NetID
- [x] Extended data


This packet is known as variant packet. It contains in extended data format known as VariantList which is comming from ProtonSDK. First item in VariantList is always a string which is name of function which should be executed.
