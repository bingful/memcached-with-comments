# Memcached With Comment

## 简介
Memcahced中文注释版

以/**开头的注释是增加的注释

## 存储结构
cache
├── item
│   ├── slab
│   │   ├── chunk
│   │   └── ...
│   └── ...
└── ...

## 执行流程
item_get(key_token->value, key_token->length) (memcached.c) -->
hv = hash(key, nkey), item_get (key, nkey) (thread.c) -->
do_item_get (items.c) -->
assoc_find (key, nkey, hv) (assoc.c)

## 文件结构
.
├── assoc.c //memcached根据key操作item
├── assoc.h //memcached根据key操作item 头文件
├── autogen.sh //检查autoconf依赖, 执行autoconf相关命令生成configure文件
├── cache.c //memcached操作cache对象
├── cache.h //memcached操作cache对象 头文件
├── configure.ac //autoconf配置文件
├── daemon.c //创建守护进程
├── devtools
│   ├── bench_noreply.pl
│   └── clean-whitespace.pl
├── doc //文档相关, make生成PDF文档
├── globals.c //声明全局变量
├── hash.c //hash表初始化操作
├── hash.h //hash表初始化操作 头文件
├── items.c //memcached操作item
├── items.h //memcached操作item 头文件
├── jenkins_hash.c //jenkins hash 算法
├── jenkins_hash.h //jenkins hash 算法头文件
├── m4
│   └── c99-backport.m4
├── Makefile.am //make配置文件
├── memcached.c //主文件(网络请求, 消息队列等相关方法)
├── memcached_dtrace.d //DTrace工具相关申明
├── memcached.h //主头文件(网络请求, 消息队列等相关方法)
├── memcached.spec.in //rpm打包相关说明
├── murmur3_hash.c //murmur3 hash 算法
├── murmur3_hash.h //murmur3 hash 算法头文件
├── protocol_binary.h //二进制协议头文件
├── sasl_defs.c //sasl 认证相关调用
├── sasl_defs.h //sasl 认证相关调用 头文件
├── scripts //操作相关脚本
│   ├── damemtop //memcached服务负载信息(perl)
│   ├── damemtop.yaml //memcached服务负载信息配置文件
│   ├── mc_slab_mover //memcached服务SLAB(perl)
│   ├── memcached-init //memcached服务启动/停止/重启/强制重启脚本
│   ├── memcached.service
│   ├── memcached.sysv //配置memcache服务
│   ├── memcached-tool //查看memcached状态,配置等信息(perl)
│   ├── README.damemtop
│   └── start-memcached //开启memcached服务,创建守护进程(perl)
├── sizes.c //memcached sizes 操作
├── slabs.c //memcached操作slab
├── slabs.h //memcached操作slab 头文件
├── solaris_priv.c //在solaris系统放弃权限
├── stats.c //memcached stats 操作
├── stats.h //memcached stats 操作 头文件
├── t //测试相关脚本
├── thread.c //memcached线程库(接收网络请求->调度线程->操作item)
├── timedrun.c //timedrun 调试工具(不停fork子进程执行程序)
├── trace.h //debug模式下trace相关方法声明
├── util.c //效率方法
├── util.h //效率方法
├── version.pl //生成版本文件
└── version.sh //生成版本文件

## 已完成

## 贡献成员

* 丁靖
* 祁冰
