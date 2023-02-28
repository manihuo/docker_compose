# docker_compose
自定义docker-compose.yml相关环境

使用时记得调整 docker-compose.yml 中的本地路径，连接本地redis、mysql等服务，需要根据本地网络ip访问 127.0.0.1 无效


#### 安装gd扩展
```
#gd扩展需要依赖其他服务，镜像运行后直接在容器中加载
1.进入容器
    docker exec -it 容器名称 bash
2.更新软件源
    apt update
3.安装依赖库
    apt install -y libwebp-dev libjpeg-dev libpng-dev libfreetype6-dev
4.解压源码
    docker-php-source extract
5.进入gd源码文件夹
    cd /usr/src/php/ext/gd
6.准备编译
    docker-php-ext-configure gd --with-webp-dir=/usr/include/webp --with-jpeg-dir=/usr/include --with-png-dir=/usr/include --with-freetype-dir=/usr/include/freetype2
7.编译安装
    docker-php-ext-install gd
8.检查扩展是否安装成功
    php -m | grep gd
9.退出php容器终端
    exit
10.关闭xxx/php/ext扩展目录
    docker-php-source delete
11.重启php容器
    docker container restart 容器名称
```
