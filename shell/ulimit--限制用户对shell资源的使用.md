用法  
ulimit [opt] [配额]

opt | 含义
-H | hard limit,严格的设置,必定不能超过这个设置的数值
-S | soft limit,警告设置,可以超过这个值,但超过后就有警告信息
-a | 列出所有限制额度
-c | 限制进程崩溃后产生的内核文件(core file)的大小
-f | 此shell可创建的文件的最大大小,单位为KB
-d | 进程可使用的最大断裂内存(segment)
-l | 可锁定的内存容量
-t | 可使用的最大cpu时间,单位为秒
-u | 单一用户可使用的最大进程数


经验技巧  
1 想要复原ulimit的设置最简单的方法是注销后再登陆,否则就要重新以ulimit设置  
2 普通用户如果以ulimit -f设置了文件大小,则只能继续减小文件容量