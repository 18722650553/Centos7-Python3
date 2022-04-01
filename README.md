# Centos7安装并配置Python3环境 #

CentOS7自带的有python环境， 但是版本是2.7

1. 查看Python的位置
```
# whereis python
```

2. 安装相关包
```
# yum install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gcc make libffi-devel

```

3. 使用wget下载Python3源码包
```
# wget http://npm.taobao.org/mirrors/python/3.9.9/Python-3.9.9.tar.xz
```

4. 编译Python3源码包
```
# xz -d Python-3.9.9.tar.xz
# tar -xf Python-3.9.9.tar
#进入解压后的目录，依次执行下面命令进行手动编译
# cd Python-3.9.9
# ./configure prefix=/usr/local/python3
# make && make install
```

5. 添加软链接
```
#将原来的链接备份
# mv /usr/bin/python /usr/bin/python.bak
#添加python3的软链接
# ln -s /usr/local/python3/bin/python3. /usr/bin/python
#测试是否安装成功了
# python -V
```

6.  更改yum配置
```
vi /usr/bin/yum
把#! /usr/bin/python修改为#! /usr/bin/python2
 
vi /usr/libexec/urlgrabber-ext-down
把#! /usr/bin/python 修改为#! /usr/bin/python2
```

7. 启动
```
#启动python2
# python2
#启动python3
# python3
```
