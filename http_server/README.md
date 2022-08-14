# HTTP server

You will need to have setup mostly any HTTP server on port 80, which accepts POST request.

This server will be really simple as it needs to respond with single page. The request URL is `http://growtopia1.com/growtopia/server_data.php`
or when alternative URL is requested, then `http://growtopia2.com/growtopia/server_data.php`.

You might of course notice that you don't own domain `growtopia1.com` nor `growtopia2.com`, so you will have to use clever trick.
There are few possibilities, but most common is modifying system file called `/etc/hosts/` to route all requests from those domains
to our own IP address. But you also have variety of others, like using your own DNS server or modyfying growtopia executable.

**NOTE**: Growtopia V3.92 and up use an HTTPS server instead, so host one on port 443 too (not the same as an HTTP server!)

But now let's look at an example of the server data:

```
server|127.0.0.1
port|17091
type|1
#maint|Maintenance message

beta_server|127.0.0.1
beta_port|17091

beta_type|1
meta|localhost
RTENDMARKERBS1001
```

Below is a detailed explanation of it all:

`server` - IP adress to which should client connect.
`port` - Port to which should client connect.
`type` - I have no idea what it does.
`maint` - This is maintenance message, if you remove `#` in front of it, then it will show this text. It is usually used when your ENet server is down.
`beta_sever` - Same as `server`, but used when client is in beta mode.
`beta_port` - Same as `port`, but used when client is in beta mode.
`beta_type` - Same as `type`, but used when client is in beta mode.
`meta` - This is string which is put into logging packet, used to verify the authenticity of the logon packet in real GT.
`RTENDMARKERBS1001` - This is marker for end of data (it is from Proton SDK).

Use `\n` character to separate those lines and not `\r\n`. (i.e. use UNIX encoding when saving the server data file)

