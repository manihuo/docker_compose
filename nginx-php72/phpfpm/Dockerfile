FROM php:7.2.22-fpm-stretch
COPY redis-5.3.6 /usr/src/php/ext/redis
COPY xdebug-3.1.4 /usr/src/php/ext/xdebug
RUN docker-php-source extract  \
    && docker-php-ext-install bcmath pdo_mysql redis xdebug\
    && docker-php-source delete \
    && echo '[PHP]\ndate.timezone = Asia/Shanghai\n' > /usr/local/etc/php/conf.d/tzone.ini



#加载 redis、pdo_mysql、bcmath 扩展
#gd扩展需要依赖其他服务，镜像运行后直接在容器中加载
      # 进入容器
    #  docker exec -it 容器名称 bash
      # 更新软件源
    #  apt update
      # 安装各种库
    #  apt install -y libwebp-dev libjpeg-dev libpng-dev libfreetype6-dev
      # 解压源码
    #  docker-php-source extract
      # 进入gd源码文件夹
    #  cd /usr/src/php/ext/gd
      # 准备编译
    #  docker-php-ext-configure gd --with-webp-dir=/usr/include/webp --with-jpeg-dir=/usr/include --with-png-dir=/usr/include --with-freetype-dir=/usr/include/freetype2
      # 编译安装
    #  docker-php-ext-install gd
      # 检查扩展是否安装成功
    #  php -m | grep gd
      # 退出php容器终端
    #  exit
      # 重启php容器
    #  docker container restart 容器名称