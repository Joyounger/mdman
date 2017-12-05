

locate指令利用事先建立的系统中所有文件名称及路径的locate数据库实现快速定位给定的文件.
locate指令无需

选项 | 功能
-- | --
-c/--count | 不将文件名输出到终端上,而是只显示符合条件的文件数目
-d <目录> 或 --database = <目录> | 指定存放locate数据库的目录
-i | 忽略文件名大小写差异
-q | 忽略错误信息
-n <数字> | 设定最多输出查找结果
-r <正则表达式>或--regexp=<正则表达式> | 进行查找匹配时,使用基本的POSIX正则表达式

经验  
1 由于locate指令基于数据库进行查询,所以第一次运行前,要用updatedb指令创建locate数据库  
2 locate指令的数据库需要定期执行,以提高locate指令的准确性.大多数发型版都设置了自动调用updatedb指令来更新数据库  
3 slocate时GNU locate的安全增强版,大多数linux发行版中考虑到与unix的兼容性,locate实际是slocate的符号链接