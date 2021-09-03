# conda常用命令
命令|注释
:--|:--
conda update -n base conda|update最新版本的conda
conda create -n xxx python=3.6|创建python3.6的xxx虚拟环境
conda activate xxx|开启xxx环境
conda deactivate xxx|关闭xxx环境
conda env list|显示所有的虚拟环境
conda info --envs|显示所有的虚拟环境
conda search xxx|检索包xxx
conda install --channel https://conda.anaconda.org/anaconda tensorflow=1.8.0|安装指定版本的tensorflow
conda list|查看已经安装的文件包
conda list -n xxx|查看xxx虚拟环境下已经安装的文件包
conda update xxx|更新xxx虚拟环境下安装的文件包
conda uninstall xxx|卸载xxx文件包
conda remove -n xxx -all|删除xxx虚拟环境
conda clean -p|删除没用的文件包
conda clean -t|删除tar包
conda clean -y ==all|删除所有的安装包及cache
conda create --name newname --clone oldname|克隆oldname环境为newname环境
conda remove --name oldname --all|彻底删除旧环境
conda config --show channels|显示目前conda的数据源有哪些
conda config --add channels xxx|添加地址为xxx的数据源
conda config --set show_channels_urls yes|显示数据源
conda config --remove channels xxx|删除地址为xxx的数据源