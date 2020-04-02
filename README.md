# ubuntu-QT4

该项目基于ubuntu-14.04-I386和ubuntu-14.04-arm系统环境
QT4编译环境

1、生产make文件： 切换到项目目录执行 qmake ./项目配置文件

2、执行gcc编译： make

3、 生成安装： /usr/local/installjammer/installjammer --build-dir PATH --build PATH/file.mpi 编译生成安装包

4、 由于容器是32位系统，而宿主机内核是64位， installjammer 脚本获取系统信息不符，导致编译运行失败
   修改，在dockerfile中添加系统环境变量 installjammer读取该环境变量