# conda使用中的问题
问题|原因|解决
--|--|--
conda无法创建虚拟环境并且无法安装其他第三方包|默认镜像源访问速度过慢，会导致超时从而导致更新和下载失败|win+R输入%HOMEPATH%找到.condarc文件替换为：清华源









```
.condarc文件中的清华源
channels:
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
show_channel_urls: true
ssl_verify: false
```