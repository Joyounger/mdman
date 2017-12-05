用法  





经验技巧  
1 reboot,halt,poweroff调用的库函数差不过,都可以用来重启和关机,,man page也放在一起  
shutdown可以依据目前已启动的服务来依次关闭各服务,halt则不考虑系统状态,直接硬件关机
  
2 一般在用命令重启时,使用
$ sync; sync; sync; reboot
