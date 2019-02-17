


wget可下载远程网页和文件


选项 | 含义
---|---
-t | 指定重试次数
-o | 指定日志文件




示例
1 wget url1 url2 url3
指定从多个url下载

2 用wget下载文件时,可以用-O指定下载的文件名




经验技巧
1 断点续传
如果使用wget进行的下载在完成前被中断,可以用-c断点续传
wget -c URL
2 复制或镜像整个网站
wget --miror exampledomain.com
or
wget -r -N -1 DEPTH URL
-l指定页面层级DEPTH,