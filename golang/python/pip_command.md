# python包管理工具pip命令详细

命令|命令详细
--|--
pip help|帮助信息
pip version|版本及路径信息
pip install SomePackage|安装包
pip install SomePackage>=1.0.1|安装最小版本
pip install --upgrade SomePackage|升级包
pip install --upgrade pip|linux或mac下升级pip；python2.x
pip3 install --upgrade pip|Linux或mac下升级pip；python3.x
python -m pip install -U pip|Windows下升级pip；python2.x
python -m pip3 install -U pip|Windows下升级pip；python3.x
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package|临时使用清华镜像进行安装
pip unstall SomePackage|卸载安装包
pip show -f SomePackage|查看包详细信息
pip list|列出已安装的包

pip国内镜像|url
--|--
阿里云镜像源|http://mirrors.aliyun.com/pypi/simple/
中国科技大学镜像源|https://pypi.mirrors.ustc.edu.cn/simple/ 
豆瓣镜像源|http://pypi.douban.com/simple/ 
清华大学镜像源|https://pypi.tuna.tsinghua.edu.cn/simple/
中国科学技术大学镜像源|http://pypi.mirrors.ustc.edu.cn/simple/