# docker命令
* 搜索image:docker search tutorial
* 下载image:docker pull learn/tutorial
* 容器中运行:docker run learn/tutorial echo "hello word"
* 容器中安装新命令:docker run learn/tutorial apt-get install -y ping
* 保存对容器的修改:docker ps ls     docker commit 容器ID(前三位即可) learn/ping
* 检查运行中的容器:docker inspect 容器ID(前三位即可)
* 发布image:docker push learn/ping

