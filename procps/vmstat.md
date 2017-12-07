vmstat可以检测cpu/内存/磁盘输入输出状态等

用法  
vmstat [-a] [延迟 [总计检测次数]]  
vmstat [-fs]  内存相关  
vmstat [-S 单位] 设置显示数据的单位  
vmstat [-d] 与磁盘有关  

opt | 含义
-a | 使用inactive/active(活跃与否)替代buffer/cache的内存输出信息
-f | 开机到目前为止系统复制(fork)的进程数
-s | 将一些事件(开机到目前为止)导致的内存变化情况列表说明
-S | 后面可以接单位,让显示的数据有单位,例如K/M
-d | 列出磁盘的读写总量统计表
-p | 后面列出分区,可显示该分区的读写总量统计表


输出:
$ vmstat  
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----  
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st  
进程字段(procps)中:  
r:等待运行中的进程数 b:不可被唤醒的进程数 这两个数越多代表系统越忙碌
memory字段:  
这部分与free的输出相同,swpd:虚拟内存被使用的数量 free:未被使用的内存数量 buff:用于缓存存储器
cache:用于高速缓存  
交换空间(swap)中:  
si:磁盘中将程序取出的量 so:由于内存不足而将没用到的程序写入到磁盘的swap的容量.如果si/so数值太大,表示内存
内的数据经常得在磁盘与内存之间传来传去  
io中:
bi:由磁盘写入的块数量
system中  
in:每秒被中断的进程次数 cs:每秒进行的事件切换次数  这两个值越大,代表系统与接口设备(网卡,磁盘等)的通信非常频繁  
cpu中:
us:非内核层的cpu使用状态 sy:内核层cpu使用状态 id:闲置状态
wa:等待io所耗费的cpu状态 st:被虚拟机所盗用的cpu状态



