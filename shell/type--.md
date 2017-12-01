 type [-afptP] 名称 [名称 ...]  
不加任何参数时,type会显示出命令是外部命令还是bash内置命令

选项 | 功能
-- | --
-t | 返回下列词中的任何一个 `alias'、`keyword'、`function'、`builtin'、`file' 或者 `'，相应地如果 NAME 是一个别名、shell 保留字、shell 函数、shell 内建、磁盘文件(即外部命令)或没有找到
-p | 如果后接的name为外部命令时,显示出可执行文件的完整路径  
-f | 抑制 shell 函数查询
-a | 由PATH变量定义的路径中,将所有含name的命令都列出来,包含alias


经验技巧  
1 type -a cmd如果查找到多个结果,在shell下执行cmd时的查找顺序就是type的显示顺序.一般shell内置命令都在普通命令前