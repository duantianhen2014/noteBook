# PHP -- The best language

<!-- TOC -->

- [PHP -- The best language](#php----the-best-language)
    - [一、PHP是什么](#一php是什么)
    - [二、PHP安装](#二php安装)
        - [1、yum安装](#1yum安装)
    - [2、apt安装](#2apt安装)
        - [3、源码安装](#3源码安装)
    - [三、PHP 基础](#三php-基础)
        - [1、类型](#1类型)
        - [2、变量](#2变量)
        - [3、常量](#3常量)
        - [4、表达式](#4表达式)
        - [5、运算符](#5运算符)
        - [6、流程控制](#6流程控制)
        - [7、函数](#7函数)
    - [四、PHP 进阶](#四php-进阶)
        - [1、类与对象](#1类与对象)
        - [2、命名空间](#2命名空间)
        - [3、异常处理](#3异常处理)
        - [4、生成器](#4生成器)
        - [5、预定义变量/异常/接口/](#5预定义变量异常接口)
        - [6、上下文（Context）选项和参数](#6上下文context选项和参数)
    - [五、PHP 实践](#五php-实践)
        - [1、多维数组变一维数组](#1多维数组变一维数组)
    - [六、PHP 面试](#六php-面试)
    - [七、PHP扩展](#七php扩展)
    - [八、PHP优化](#八php优化)
    - [九、Modern PHP](#九modern-php)
    - [十、参考资料](#十参考资料)
    - [十一、php大厂](#十一php大厂)

<!-- /TOC -->

## 一、PHP是什么

PHP（全称：PHP：Hypertext Preprocessor，即“PHP：超文本预处理器”）是一种开源的通用计算机脚本语言，尤其适用于网络开发并可嵌入HTML中使用。PHP的语法借鉴吸收C语言、Java和Perl等流行计算机语言的特点，易于一般程序员学习。PHP的主要目标是允许网络开发人员快速编写动态页面，但PHP也被用于其他很多领域。

## 二、PHP安装

### 1、yum安装

```sh
# php7.1
rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm
rpm -Uvh https://mirror.webtatic.com/yum/el6/latest.rpm

yum -y install php71w-fpm php71w-opcache php71w-cli php71w-common php71w-dba php71w-devel php71w-embedded php71w-enchant php71w-gd php71w-imap php71w-interbase php71w-intl php71w-ldap php71w-mbstring php71w-mcrypt php71w-mysqlnd php71w-odbc php71w-pdo php71w-pdo_dblib php71w-pear  php71w-pecl-imagick php71w-pecl-memcached php71w-pecl-mongodb php71w-pecl-redis php71w-pecl-xdebug php71w-pgsql php71w-phpdbg php71w-process php71w-pspell php71w-recode php71w-snmp php71w-soap php71w-tidy php71w-xml php71w-xmlrpc
```

## 2、apt安装

```bash
apt -y install php php-pear php-fpm php-dev php-zip php-curl php-xmlrpc php-gd php-mysql php-mbstring php-xml libapache2-mod-php

```

### 3、源码安装

```bash
# 下载
wget http://hk1.php.net/get/php-7.2.10.tar.gz/from/this/mirror php-7.2.10.tar.gz
# 解压
tar -zxf php-7.2.10.tar.gz php-7.2.10
# 依赖
apt -y install \
build-essential \
gcc \
g++ \
autoconf \
libiconv-hook-dev \
libmcrypt-dev \
libxml2-dev \
libmysqlclient-dev \
libcurl4-openssl-dev \
libjpeg8-dev \
libfreetype6-dev \
libssl-dev
# 编译
./configure --prefix=/usr/local/php7.2 \
--with-config-file-path=/etc/php7.2 \
--enable-fpm \
--enable-pcntl \
--enable-mysqlnd \
--enable-opcache \
--enable-sockets \
--enable-sysvmsg \
--enable-sysvsem \
--enable-sysvshm \
--enable-shmop \
--enable-zip \
--enable-soap \
--enable-xml \
--enable-mbstring \
--disable-rpath \
--disable-debug \
--disable-fileinfo \
--with-mysqli=mysqlnd \
--with-pdo-mysql=mysqlnd \
--with-pcre-regex \
--with-iconv \
--with-zlib \
--with-gd \
--with-openssl \
--with-mhash \
--with-xmlrpc \
--with-curl \
--with-imap-ssl
# 安装
make && make install
# 输出
Build complete.
Don't forget to run 'make test'.

Installing shared extensions:     /usr/local/php7.2/lib/php/extensions/no-debug-non-zts-20170718/
Installing PHP CLI binary:        /usr/local/php7.2/bin/
Installing PHP CLI man page:      /usr/local/php7.2/php/man/man1/
Installing PHP FPM binary:        /usr/local/php7.2/sbin/
Installing PHP FPM defconfig:     /usr/local/php7.2/etc/
Installing PHP FPM man page:      /usr/local/php7.2/php/man/man8/
Installing PHP FPM status page:   /usr/local/php7.2/php/php/fpm/
Installing phpdbg binary:         /usr/local/php7.2/bin/
Installing phpdbg man page:       /usr/local/php7.2/php/man/man1/
Installing PHP CGI binary:        /usr/local/php7.2/bin/
Installing PHP CGI man page:      /usr/local/php7.2/php/man/man1/
Installing build environment:     /usr/local/php7.2/lib/php/build/
Installing header files:          /usr/local/php7.2/include/php/
Installing helper programs:       /usr/local/php7.2/bin/
  program: phpize
  program: php-config
Installing man pages:             /usr/local/php7.2/php/man/man1/
  page: phpize.1
  page: php-config.1
Installing PEAR environment:      /usr/local/php7.2/lib/php/
[PEAR] Archive_Tar    - installed: 1.4.3
[PEAR] Console_Getopt - installed: 1.4.1
[PEAR] Structures_Graph- installed: 1.1.1
[PEAR] XML_Util       - installed: 1.4.2
[PEAR] PEAR           - installed: 1.10.5
Wrote PEAR system config file at: /usr/local/php7.2/etc/pear.conf
You may want to add: /usr/local/php7.2/lib/php to your php.ini include_path
/home/vps/php-7.2.10/build/shtool install -c ext/phar/phar.phar /usr/local/php7.2/bin
ln -s -f phar.phar /usr/local/php7.2/bin/phar
Installing PDO headers:           /usr/local/php7.2/include/php/ext/pdo/
# 配置
mkdir /etc/php7.2
cp php.ini-development /etc/php7.2/php.ini
export PATH=/usr/local/php7.2/bin:$PATH
export PATH=/usr/local/php7.2/sbin:$PATH
source ~/.bashrc
# 测试
php -v
```

## 三、PHP 基础

### 1、类型

    Boolean 布尔类型
    Integer 整型
    Float 浮点型
    String 字符串
    Array 数组
    Object 对象
    Resource 资源类型
    NULL
    Callback / Callable 类型

### 2、变量

### 3、常量

### 4、表达式

### 5、运算符

### 6、流程控制

### 7、函数

## 四、PHP 进阶

### 1、类与对象

### 2、命名空间

### 3、异常处理

### 4、生成器

### 5、预定义变量/异常/接口/

### 6、上下文（Context）选项和参数

## 五、PHP 实践

### 1、多维数组变一维数组

```php

$result = [];
//无键值对
array_walk_recursive($arr, function($value) use (&$result) {
    array_push($result, $value);
});
//有键值对
array_walk_recursive($arr, function($value) use (&$result) {
    array_push($result, array_values($value));
});

```

## 六、PHP 面试

[PHP面试](php/level)

## 七、PHP扩展

按phpinfo()上的扩展解读

- date 时间库
- dom/xml/SimpleXML/libxml xml操作库
- exif 相机库
- fileinfo 文件相关库
- filter 参数过滤库
- ftp ftp库
- gd 图像库
- hash hash算法库
- iconv 字符串转换库
- imagick 图像库
- json json操作库
- mbstring 多字节字符串操作库
- memcached 缓存库
- mongodb 数据库
- mysqli 数据库
- mysqlnd 数据库
- openssl 加密库
- pcre 正则库
- PDO 数据库
- Phar 包
- posix 多进程库
- readline 交互库
- redis 缓存库
- Reflection 反射库
- session 会话库
- SPL 标准库
- swoole 异步库
- tokenizer 标记库
- xdebug debug库
- Zend OPcache 缓存库
- zlib 压缩库

## 八、PHP优化

## 九、Modern PHP

[Modern PHP](php/modern)

## 十、参考资料

[php手册](http://php.net/)

## 十一、php大厂

- 北京
  - 阿里文娱
  - 腾讯
  - 百度
  - 聚美优品
  - 掌阅
  - 好未来
  - 小米
  - 凤凰网
  - 联想集团
  - 陌陌
  - 京东
  - 新浪微博
  - 奇虎360
  - 猎豹移动
  - 苏宁
  - 世纪佳缘
  - 搜狗
  - 高德地图
  - 当当
  - 爱奇艺
  - 链家
  - 房天下
  - 51talk
  - 马蜂窝
  - 滴滴出行
  - 饿了么
  - 作业帮
  - ofo
  - 穷游网
  - 欧朋浏览器
  - 好大夫
  - 借贷宝
  - 什么值得买
  - 自如
  - 36氪
  - 懂球帝
  - 慕课网
  - 乐视
  - 美图
  - 顺丰
  - 金山云
  - 贝壳
  - 蛋壳公寓
- 上海
  - 腾讯
  - 哔哩哔哩
  - 百度
  - 阅文集团
  - 虎扑
  - 车轮
  - 游族网络
  - 京东
  - 2345.com
  - 巨人网络
  - 唯品会
  - 安居客
  - 百姓网
  - 51job
  - 蜻蜓FM
  - wifi万能钥匙
- 杭州
  - ABC360
  - 丁香园
  - 婚礼纪
  - 要出发
  - 同花顺
  - 战旗直播
  - 电魂
  - 磐石网盟
  - 贝贝网
- 深圳
  - 腾讯
  - 货拉拉
  - 美图
  - 环球易购
  - 百度
  - 威锋网
  - 乐逗游戏