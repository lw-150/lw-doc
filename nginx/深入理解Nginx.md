# 深入理解Nginx笔记
1. 使用Nginx必备软件
  * GCC编译器,C语言编辑器：yum install -y gcc
  * G++编译器，C++语言编译器：yum install -y gcc-c++
  * PCRE库，正则表达式：yum install -y pcre pcre-devel
  * zlib库，gzip压缩：yum install -y zlib zlib-devel
  * OpenSSL开发库，https协议：yum install -y openssl openssl-devel
2. linux内核参数调优：待整理
3. 源码安装Nginx
    * tar -zxvf ngin-1.14.tar.gz
    * ./configure & make & make install
4. 