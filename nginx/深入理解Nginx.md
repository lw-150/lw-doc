# 深入理解Nginx笔记
## Nginx安装使用
* 使用Nginx必备软件
  * GCC编译器,C语言编辑器：yum install -y gcc
  * G++编译器，C++语言编译器：yum install -y gcc-c++
  * PCRE库，正则表达式：yum install -y pcre pcre-devel
  * zlib库，gzip压缩：yum install -y zlib zlib-devel
  * OpenSSL开发库，https协议：yum install -y openssl openssl-devel
* linux内核参数调优：待整理
* 源码安装Nginx
  * tar -zxvf ngin-1.14.tar.gz
  * ./configure & make & make install
## Nginx参数详细
### Nginx配置结构
```
... 全局配置
events {
  ... event配置模块
  ... event参数
}
http {
  include ...
  ... http参数
  upstream mystr{

  }
  server {
    ... server参数
    location {

    }
    location {

    }
  }
  if {

  }
}
```
### 全局配置
* daemon on|off
  * 是否以守护进程方式运行
  * 默认：on
* master_process on|off
  * 是否以master/worker方式工作
  * 默认：on
* error_log pathfile level
  * error日志设置
  * 默认：logs/error.log error
  * 日志输出级别：debug,info,notice,warn,error,crit,alert,emerg
* work_rlimit_core size
  * 限制coredump（核心转储）文件的大小
  * linux系统中，当进程发生错误或收到信号终止时，系统会将进程执行时的内存内容吸入一个文件，这就是coredumps（核心转储）
* work_directory path
  * 指定coredump文件生成目录
* pid path/file
  * 保存master进程ID的pid文件存放路径
  * 默认：与configure执行时的参数--pid-path指定的路径相同
* use username groupname
  * Ngxin worker进程运行的用户及用户组
  * 默认：use nobody nobody
* work_rlimit_nofile limit
  * Nginx worker进程可以打开的最大句柄描述符个数
* work_rlimit_sigpending limit
  * 用户发往Nginx信号队列的大小
* worker_processes number
  * Nginx worker进程个数
  * 默认：auto
  * 一般设定为CPU内核个数
* worker_cpu_affinity cpumask
  * 绑定Nginx woker进程到指定的cpu内核
  * 好处：方式多个worker进程抢同一个cpu内核
  * 示例：四个内核，worker_cpu_affinity 1000 0100 0010 0001
* ssl_engine device
  * 可以用OpenSSL提供的命令查看是否有SSL硬件加速设备：openssl engine -t
* timer_resolution t
  * 系统调用gettimeofday的执行频率
  * 默认情况下， 每次内核的事件调用返回时，都会执行一次gettimeofday，实现用内核的时钟来更新Nginx中的缓存时钟
* worker_priority nice
  * Nginx worker进程优先级设置
  * 默认：0，worker_priority 0;
  * 取值范围：-20到19，-20优先级最高
  * 如果希望Nginx占用更多系统资源，可以调高进程优先级，但不建议小于内核进程的优先级（通常为-5），即：大于-5

### events模块配置
* debug_connection IP|CIDR
  * 仅对指定客户端输出debug日志
  * 示例：debug_connection 10.32.156.0/24;
  * debug_connection生效，需执行configure时加入--with-debug参数
* accept_mutex on|off
  * 是否打开accept锁（负载均衡锁）
  * 默认：on
* lock_file path/file
  * lock文件路径
  * 默认：logs/nginx.lock
* accept_mutex_delay Nms
  * 使用accept锁后到真正建立连接之间的延迟事件
  * 默认：500ms
* muli_accept on|off
  * 批量建立新连接
  * 默认off
* use 事件模型
  * Nginx会自动使用最合适的事件模型
  * 事件模型：kqueue,rtsig,epoll,dev/poll,select,poll,eventport
  * Linux系统epoll性能最高
* work_connections number
  * 每个woker的最大连接数
### HTTP模块配置
*  
