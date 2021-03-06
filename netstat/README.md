
```bash
# Ubuntu 上查看TCP/UDP监听端口
netstat -lnp -t
netstat -lnp -u
-l Show only listening sockets.
-n Show numerical addresses instead of trying to determine symbolic host, port or user names.
-p Show the PID and name of the program to which each socket belongs.
-t TCP
-u UDP

# MacOS 上查看TCP/UDP监听端口 (不同操作系统上的netstat不一样)
netstat -ln -p tcp
netstat -ln -p udp
-l Print full IPv6 address.
-n Show network addresses as numbers
-p Show statistics about protocol, which is either a well-known name for a protocol or an alias for it.

# Ubuntu 使用 ss 工具查看监听端口
ss -lpt
ss -lpu
-l Display only listening sockets
-a Display both listening and non-listening
-p Show process using socket.
-t Display TCP sockets.
-u Display UDP sockets.

# Ubuntu 使用 lsof 工具查看监听端口
lsof -iTCP -sTCP:LISTEN -P -n
-i selects  the listing of files any of whose Internet address matches the address
-s alone directs lsof to display file size at all times.
-P inhibits the conversion of port numbers to port names for network files.
-n inhibits the conversion of network numbers to host names for network files. 
```