dirname很少直接在shell命令行中使用，我一般把它用在shell脚本中，用于取得脚本文件所在目录，然后将当前目录切换过去。  
$(cd $(dirname "$0");pwd)