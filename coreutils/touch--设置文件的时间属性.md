用法  
touch [opt] 文件  




touch指令有两个功能:  
1 用于改变文件的时间属性,它将文件的最后访问时间和最后修改时间设置为系统当前时间  
2 用来创建新的空文件  

选项 | 功能
-- | --
-t <时间> | 用指定的时间设置给定文件的时间属性.指定时间时的格式为 MMDDhhmm[[CC]YY][.ss] 含义依次为 月,日,小时,分钟,世纪,年,秒
-a <时间> | 将指定文件的最后访问时间设置为当前系统时间,其他时间属性不变
-c或--no-create | 仅修改文件时间,如果文件不存在则不创建
-m <时间> | 仅将文件的最后修改时间设置为当前系统时间
-d <字符串>或--date=<字符串> | 使用字符串所代表的时间来设置文件的时间属性  


经验  
1 linux中没有单独的指令用来创建新的空文件,使用touch新建的文件最后访问时间和最后修改时间均为当前系统时间  
2 复制文件时不会复制ctime,ctime记录的是文件的状态而非内容被改变的时间

