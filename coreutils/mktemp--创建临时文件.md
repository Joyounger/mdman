











经验技巧:
1 创建临时文件:
filename=`mktemp`
echo $filename
创建临时目录:
dirname=`mktemp -d`
echo $dirname
进行生成文件名,不希望实际创建文件或目录:
tmpfile=`mktemp -u`
echo $tmpfile
根据模板创建临时文件名:
$ mktemp test.XXX #保证至少有3个'X'字符,执行时X会被随机字符替换
test.9lv


