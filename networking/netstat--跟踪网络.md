用法  
 netstat [选项]
 

选项 | 含义
---|---
-a | 将目前系统上所有的连接,监听,socket数据都列出
-t | 列出tcp网路数据包的数据
-u | 列出udp网路数据包的数据
-n | 不列出进程的服务名称,以端口号显示
-l | 列出目前正在网络监听的服务
-p | 列出该网络服务的pid


输出中主要分为两部分  
1 网络的连接Active Internet connections  
proto:数据包协议  
recv-q:The count of bytes not copied by the user program connected to this socket.  
send-q:The count of bytes not acknowledged by the remote host.  
local address:Address and port number of the local end of the socket.    
Foreign Address:Address and port number of the remote end of the socket.  
State: The state of the socket.  
2 本机进程相关Active unix domain sockets  
proto:一般是unix
refcnt:连接到此socket的进程数量
flags:进程标识  
type:socket访问的类型,主要有需要确认连接的stream和不需要确认的dgram  
state:若为connectd表示多个进程之间已经建立连接
path:连接到此socket的相关程序路径,或相关数据输出路径



