<p align="center">
    <a href="https://github.com/stelin/swoft" target="_blank">
        <img src="http://www.stelin.me/assets/img/swoft.png" alt="swoft" />
    </a>
</p>


# 简介
Swoft 是基于 Swoole 2.x 的高性能 PHP 微服务框架，内置 HTTP 服务器，框架全协程实现，性能大大优于传统的 PHP-FPM 模式。

- 基于 Swoole 扩展
- 内置 HTTP 协程服务器
- MVC 分层设计
- 高性能路由
- 全局容器注入
- 高性能 RPC
- 别名机制
- 事件机制
- 国际化(i18n)
- 服务治理熔断、降级、负载、注册与发现
- 连接池 Mysql、Redis、RPC
- 数据库 ORM
- 协程、异步任务投递
- 自定义用户进程
- RPC、Redis、HTTP、Mysql 协程和同步客户端无缝切换
- Inotify 自动 Reload
- 强大的日志系统

# 系统架构

<p align="center">
    <a href="https://github.com/stelin/swoft" target="_blank">
        <img src="https://github.com/swoft-cloud/swoft-doc/blob/master/assets/images/architecture.png" alt="swoft" />
    </a>
</p>

# 文档
[**中文文档**](http://doc.swoft.org)

QQ交流群:548173319

# 环境要求
1. PHP 7.X
2. [Swoole 2.x](https://github.com/swoole/swoole-src/releases), 需开启协程和异步Redis
3. [Hiredis](https://github.com/redis/hiredis/releases)
4. [Composer](https://getcomposer.org/)
5. [Inotify](http://pecl.php.net/package/inotify) (可选)

# 安装

* `composer require swoft/framework dev-master`


# 配置
复制项目根目录的 `.env.example` 并命名为 `.env`
```
# Server
PFILE=/tmp/swoft.pid
PNAME=php-swoft
TCPABLE=true
CRONABLE=false
AUTO_RELOAD=true

# HTTP
HTTP_HOST=0.0.0.0
HTTP_PORT=80

# TCP
TCP_HOST=0.0.0.0
TCP_PORT=8099
TCP_PACKAGE_MAX_LENGTH=2048
TCP_OPEN_EOF_CHECK=false

# Crontab
CRONTAB_TASK_COUNT=1024
CRONTAB_TASK_QUEUE=2048

# Settings
WORKER_NUM=1
MAX_REQUEST=10000
DAEMONIZE=0
DISPATCH_MODE=2
LOG_FILE=@runtime/swoole.log
TASK_WORKER_NUM=1
```

## 启动

**帮助命令**
```py
[root@swoft bin]# php swoft -h
 ____                __ _
/ ___|_      _____  / _| |_
\___ \ \ /\ / / _ \| |_| __|
 ___) \ V  V / (_) |  _| |_
|____/ \_/\_/ \___/|_|  \__|

Usage:
  php swoft -h

Commands:
  entity  the group command list of database entity
  rpc     the group command list of rpc server
  server  the group command list of http-server

Options:
  -v,--version  show version
  -h,--help     show help
```

**HTTP启动**

> 是否同时启动RPC服务器取决于.env文件配置

```php
// 启动服务，根据 .env 配置决定是否是守护进程
php bin/swoft start

// 守护进程启动，覆盖 .env 守护进程(DAEMONIZE)的配置
php bin/swoft start -d

// 重启
php bin/swoft restart

// 重新加载
php bin/swoft reload

// 关闭服务
php bin/swoft stop

```


**RPC启动**
> 启动独立的RPC服务器

```php
// 启动服务，根据 .env 配置决定是否是守护进程
php bin/swoft start

// 守护进程启动，覆盖 .env 守护进程(DAEMONIZE)的配置
php bin/swoft start -d

// 重启
php bin/swoft restart

// 重新加载
php bin/swoft reload

// 关闭服务
php bin/swoft stop

```

# 更新日志

[更新日志](https://github.com/swoft-cloud/swoft/blob/master/changelog.md)

# 开发成员

- [stelin](https://github.com/stelin) (swoft@qq.com)
- [inhere](https://github.com/inhere) (in.798@qq.com)
- [ccinn](https://github.com/whiteCcinn) (471113744@qq.com)
- [esion](https://github.com/esion1) (esionwong@126.com)
- [huangzhhui](https://github.com/huangzhhui) (huangzhwork@gmail.com)

# 协议
Swoft的开源协议为apache 2.0，详情参见[LICENSE](LICENSE)。
