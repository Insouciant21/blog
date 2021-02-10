---
title: 搭建自己的Hexo博客！
tags: 技术向
abbrlink: 1439757957
date: 2021-01-24 19:26:41
categories:
  - 教程
---

本文将会详细说明使用 Hexo + Vercel 来搭建个人博客，并对主题进行配置。

通过本文的学习，你将收获一个免费、简洁的个人博客，并能够熟悉搭建、写作、部署的全流程。

<!-- more -->

环境： Ubuntu 20.04

## 准备

预先安装以下程序：

- [Node.js](http://nodejs.org/)
- [Git](http://git-scm.com/)

然后准备好一个 Github 账号和一个用于存放博客文件的仓库。

如果你已经准备好了，就可以直接前往[安装 Hexo](#安装-Hexo)了。

### 安装 Git

- Windows 下直接前往[官网](https://git-scm.com/download/win)下载即可。
- Linux(Ubuntu/Debian): 执行此命令安装 `sudo apt install git`

### 安装 Node.js

前往 [Node.js 官网](https://nodejs.org/en/download/)下载安装程序，或是前往[国内镜像](https://repo.huaweicloud.com/nodejs/latest/)下载。

其他的安装方法： 使用 [nvs](https://github.com/jasongin/nvs/)。

### 安装 Hexo

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

安装只需要输入这一行命令：
```bash
npm install -g hexo-cli
# or
yarn global add hexo-cli
```
使用 `hexo -v` 验证是否成功。

## 建站

准备好一个放置博客文件的文件夹，然后执行以下命令：
```bash
hexo init <folder>
cd <folder>
npm install # or yarn 
```

`_config.yml` 是站点配置文件，你可以在此配置大部分的参数。

`source` 文件夹是资源文件夹，用于是存放用户资源。

`themes` 是主题文件夹。Hexo 会根据主题来生成静态页面。


输入 `hexo s` 然后访问 `localhost:4000` ，可以看到如下效果

![](https://i.loli.net/2021/01/24/RxaklFPZKjO6Jdt.png)

## 部署到 Vercel

{% note warning, 接下来的部分默认你已经将本地文件储存至 Github %}

首先将本地文件上传至 Github 仓库中。

进入 [Vercel 官网](https://vercel.com/signup) ，选择 `Continue with Github`

完成后在 `Import a Git Repository` 下的 `Select` 处添加 Github Account

![](https://unpkg.zhimg.com/insouciant21-oss@latest/1439757957/vercel_import1.png)

添加好账户后会出现你的仓库，从中选择你之前存放博客文件的仓库然后点击 `Import` ，例：

![](https://unpkg.zhimg.com/insouciant21-oss@latest/1439757957/vercel_import2.png)

`Import` 之后会出现这个页面，确认 `FRAMEWORK PRESET` 处为 Hexo 后就可以直接点击 `Deploy` 了。

{% image https://unpkg.zhimg.com/insouciant21-oss@latest/1439757957/vercel_framework.png alt=如果 `FRAMEWORK PRESET` 处没有显示 Hexo 请自行切换 %}

当出现烟花后你的博客就部署好了

![](https://unpkg.zhimg.com/insouciant21-oss@latest/1439757957/vercel_success.png)

### 关于自定义域名

Vercel 支持免费绑定自定义域名。

打开 Dashboard ，进入项目设置，点击 Domains 

![](https://unpkg.zhimg.com/insouciant21-oss@latest/1439757957/vercel_project_settings1.png)

然后在这里添加自己的域名

![](https://unpkg.zhimg.com/insouciant21-oss@latest/1439757957/vercel_project_settings2.png)

按照帮助添加 DNS 记录验证之后，在你的域名下会有两个蓝色的勾

![](https://unpkg.zhimg.com/insouciant21-oss@latest/1439757957/vercel_domain_success.png)

然后就可以将其他域名重定向到这个域名上了。





