用法  
1 打包与压缩  
tar [-j|-z] [cv] [-f 要创建的文件名] filename ...
2 查看压缩文件内的文件名  
tar [-j|-z] [tv] -f filename  
3 解压缩  
tar [-j|-z] [xv] [-f 压缩包] -C 目录  
仅解压特定文件的方法  
tar [-j|-z] [xv] [-f 压缩包 压缩包中要解压的文件] -C 目录  



opt | 含义
---|---
-p, --preserve-permissions, --same-permissions | 解压文件时保留文件权限属性,对于超级用户此选项默认打开
--same-owner | 解压文件时尝试保留文件的owner属性,对于超级用户此选项默认打开
-c | 创建压缩文件
-t,--list | 列出压缩包内文件
-x | 解压,可搭配-C指定解压目录
-j | bzip2支持,此时文件名最好为*.tar.bz2
-z | gzip支持,此时文件名最好为*.tar.gz
-P | 保留绝对路径,即允许备份数据中含有根目录'/'存在
--exclude=FILE | 压缩过程中排除指定文件
--exlcude-vcs | 归档时排除版本控制目录
-r |  Append files to the end of an archive. 
-t | List the contents of an archive.
-C | 解压到特定目录
--totals | 归档完后打印出总的归档字节数

经验技巧  
1 -c, -t, -x不可同时出现在一串命令行中  
2 tar压缩时不会主动设定文件扩展名,如果压缩时不用-j或-z则文件名最好用*.tar  
3 由于-f filename是紧接在一起,因此建议将-f filename与其他选项分开  
4 用-t查看压缩包内文件信息是,如果不加-v,仅列出里面文件名.如果用-v则会列出里面文件的大小权限等详细信息  
5 tar打包的文件,如果没有压缩称为tarfile, 如果还经过压缩则称为tarball  
6 用tar备份目录时备份权限等属性  
tar --same-permission --remove-files -jcv dir/ -f dir.tar.bz2
7 同一文件,用tar创建gzip压缩包后hash不一样:https://stackoverflow.com/questions/36464358/why-do-the-md5-hashes-of-two-tarballs-of-the-same-file-differ  
'tar czf outfile infiles' is equivalent to 'tar cf - infiles | gzip > outfile'
The reason the files are different is because gzip puts its input filename and modification time into the compressed file. When the input is a pipe, it uses an empty string as the filename and the current time as the modification time.
But it also has a --no-name option, which tells it not to put the name and timestamp into the file. So if you write the expanded command explicitly, instead of using the -z option to tar, you can make use of this option.
解决:tar cf - testfile | gzip --no-name > a.tar.gz  



示例  
1 解压部分文件  
解压单个文件  
tar -zxvf filename.tar.gz foder/file 解压filename.tar.gz中的文件folder/file  
解压多个文件  
tar -zxvf filename.tar.gz foder/*.txt 解压filename.tar.gz中folder下所有后缀为txt的文件  
2 解压到指定目录  
tar -zxvf filename.tar.gz foder/*.txt -C /new/dir 解压filename.tar.gz中folder下所有后缀为txt的文件到/new/dir 
3 向归档中添加文件,用-r
tar -rvf original.tar new_file
4 列出归档中的内容:
tar -t -f test.tar
如果需要在列出tar内容时获得更多细节,可以使用-v或-vv
5 归档时可以将stdout指定为输出文件,这样另一个命令就可以通过管道将它作为stdin
当通过ssh连接传文件时就很有用:
mkdir ~/dest
tar -cf - file1 file2 file3 | tar -xvf - -C ~/dest
用-c时,-f指定stdout作为归档文件
用-x时,-f指定stdin作为提取内容
6 连接归档文件
tar -Af file1.tar file2.tar # 将file1.tar file2.tar 合并为file1.tar
7 通过检测时间戳来更新归档 -u选项
8 比较归档与文件系统中的内容
tar -df archive.tar file1 file2
9 从归档中删除文件,tar -f archive.tar --delete file1 file2
10 压缩
-j bzip2
--lzma lzma格式,较新的格式,比bip2压缩率更高
如果不指定压缩格式选项,可以用-a指定让tar按扩展名自动进行压缩
11 排除文件
--exclude "pattern"













