# Laradock

> Use Docker first and learn about it later.

[![forthebadge](http://forthebadge.com/images/badges/built-by-developers.svg)](http://zalt.me)

Laradock is a Docker PHP development environment that facilitate running **PHP** Apps on **Docker**.

## Documentation

[**Full Documentation Here**](http://laradock.io)
## 介绍
LaraDock努力简化创建开发环境过程。
它包含预包装Docker镜像，提供你一个美妙的开发环境而不需要安装PHP,NGINX,MySQL和其他任何软件在你本地机器上。

**使用概览：**


让我们了解使用它安装`NGINX`, `PHP`, `Composer`, `MySQL` 和 `Redis`，然后运行`Laravel`

1. 将LaraDock放到你的Laravel项目中：
<br>
`git clone https://github.com/laradock/laradock.git`.
2. 进入LaraDock目录，然后运行这些容器。
<br>
`docker-compose up -d nginx mysql redis`
3. 打开你的`.env`文件，然后设置`mysql`的`DB_HOST` 和  `redis`的`REDIS_HOST`。
4. 打开浏览器，访问localhost：


<a name="features"></a>
### 特点

- 在PHP版本：7.0，5.6.5.5...之中可以简单切换。
- 可选择你最喜欢的数据库引擎，比如：MySQL, Postgres, MariaDB...
- 可运行自己的软件组合，比如：Memcached, HHVM, Beanstalkd...
- 所有软件运行在不同的容器之中，比如：PHP-FPM, NGINX, PHP-CLI...
- 通过简单的编写`dockerfile`容易定制任何容器。
- 所有镜像继承自一个官方基础镜像（Trusted base Images）
- 可预配置Laravel的Nginx环境
- 容易应用容器中的配置
- 干净的结构化的Docker配置文件（`dockerfile`）
- 最新的Docker Compose 版本（`docker-compose`）
- 所有的都是可视化和可编辑的
- 快速的镜像构建
- 每周都会有更新...

<a name="Supported-Containers"></a>
### 支持的软件 (容器)

- **数据库引擎:**
	- MySQL
	- PostgreSQL
	- MariaDB
	- MongoDB
	- Neo4j
- **缓存引擎:**
	- Redis
	- Memcached
- **PHP 服务器:**
	- NGINX
	- Apache2
	- Caddy
- **PHP 编译工具:**
	- PHP-FPM
	- HHVM
- **消息队列系统:**
	- Beanstalkd (+ Beanstalkd Console)
- **工具:**
	- Workspace (PHP7-CLI, Composer, Git, Node, Gulp, SQLite, Vim, Nano, cURL...)
>如果你找不到你需要的软件，构建它然后把它添加到这个列表。你的贡献是受欢迎的。

<a name="what-is-docker"></a>
### Docker是什么?

[Docker](https://www.docker.com) 是一个开源项目,自动化部署应用程序软件的容器,在Linux, Mac OS and Windows提供一个额外的抽象层和自动化的[操作系统级的虚拟化](https://en.wikipedia.org/wiki/Operating-system-level_virtualization)


<a name="why-docker-not-vagrant"></a>
### 为什么使用Docker而不是Vagrant!?

[Vagrant](https://www.vagrantup.com)构建虚拟机需要几分钟然而Docker构建虚拟容器只需要几秒钟。
而不是提供一个完整的虚拟机,就像你用Vagrant,Docker为您提供**轻量级**虚拟容器,共享相同的内核和允许安全执行独立的进程。

除了速度,Docker提供大量的Vagrant无法实现的功能。

最重要的是Docker可以运行在开发和生产(相同环境无处不在)。Vagrant是专为开发,(所以在生产环境你必须每一次重建您的服务器)。

<a name="laradock-vs-homestead"></a>
### LaraDock Homestead 对比

LaraDock and [Homestead](https://laravel.com/docs/master/homestead) 给你一个完整的虚拟开发环境。(不需要安装和配置软件在你自己的每一个操作系统)。

Homestead 是一个工具,为你控制虚拟机(使用Homestead特殊命令)。Vagrant可以管理你的管理虚容器。

运行一个虚拟容器比运行一整个虚拟机快多了**LaraDock 比 Homestead快多了**



<a name="Demo"></a>
## 演示视频
还有什么比**演示视频**好：

- LaraDock [v4.0](https://www.youtube.com/watch?v=TQii1jDa96Y)
- LaraDock [v2.2](https://www.youtube.com/watch?v=-DamFMczwDA)
- LaraDock [v0.3](https://www.youtube.com/watch?v=jGkyO6Is_aI)
- LaraDock [v0.1](https://www.youtube.com/watch?v=3YQsHe6oF80)



<a name="Requirements"></a>
## 依赖

- [Git](https://git-scm.com/downloads)                                           
- [Docker](https://www.docker.com/products/docker/)



## 使用

- Clone Laradock inside your PHP project:
```
git clone https://github.com/xiaobebe/laradock.git
```
- Enter the laradock folder and rename env-example to .env
```
cp env-example .env
```
- 修改你的.env
```
# 对应你的实际代码目录
APPLICATION=~/Code/
```
- Run your containers:
```
docker-compose up -d nginx mysql redis
```
- 数据库连接
```
host ： mysql
user ： root
pass ： root
```
- 新建站
  移动至`Nginx/sites/`

  复制`project-1.conf.example` 到 `project-1.conf`

  编辑里面的root到对应目录
  ```
  # 实际对应的目录则为 ~/Code/kod/
  root /var/www/kod;
  ```
- 重启
```
docker-compose restart
```
