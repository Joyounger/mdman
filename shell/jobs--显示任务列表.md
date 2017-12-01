


选项 | 含义
-- | --
-l | 列出进程号
-r | 仅输出运行中的任务
-s | 仅输出停止的任务

$ jobs -l  
[1]-  7088 Stopped                 vim applypatch.sh  
[2]+  3516 Stopped                 find / -print  
任务列表中,最后第三个及以后的工作,就不会有+/-符号存在了  
