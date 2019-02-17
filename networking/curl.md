

curl功能比wget更高级
和wget不同,curl并不将下载数据写入文件,而是写入stdout.
curl通常将下载文件输出到stdout,进度信息输出到stderr.



选项 | 含义
--|--
--silent | 不显示进度信息
--progress | 显示如#的进度条
-O | 将下载数据写入文件,要确保url是一个指向远程文件的url
-o | 指定文件名




经验技巧
1 和wget相抵.curl包含更高级的下载回复特性,
curl url/file -C offset
offset是以字节为单位的整数
如果只想断电续传:
curl -C -URL #curl会自动计算出应该从哪断点续传
2 只打印相应头部信息:
检查http头部的一个用例是下载之前先查看文件大小,下载之前通过检查http头部中的content-length参数来得知文件长度.
Last-Modified保存远程文件最后的改动时间
用-I或-head就可以只打印http头部信息,无须下载文件
