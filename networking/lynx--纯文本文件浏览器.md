



选项 | 含义
---|---
-dump | dumps  the  formatted  output  of  the default document or those specified on  the  command  line  to  standard  output. 



使用示例
1 以格式化纯本文形式下载网页
可以将lynx的纯文本格式化输出作为网页来获取
lynx -dump URL > webpage_as_text.txt
这个命令会将所有超链接(<a href="linl">)作为文本输出的页脚列在References标题之下
	