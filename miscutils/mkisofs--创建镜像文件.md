用法  
mkisofs [-o 镜像文件] [-rv] [-m file] 待备份文件 .. [-V vol] --graft-point=systemdir ..


选项 | 含义
---|---
-r |  通过rock ridge产生支持unix/linux的文件数据,可记录较多信息
-v | 显示构建iso文件的过程
-m file | 排除文件file,不备份到镜像文件中
-V vol | 新建volume
-graft-point | 

经验技巧  
1 默认情况下, 所有要被加到镜像文件中的文件都会被放到镜像文件中的根目录, 用-graft-point可自定义位于镜像文件中的目录,如:  
镜像文件中的目录所在=实际Linux文件系统的目录所在  
/movies/=/srv/movies/ 





