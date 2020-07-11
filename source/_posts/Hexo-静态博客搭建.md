---
title: 静态博客搭建'
toc: true
date: 2020-07-11 22:19:31
tags:
  - 博客
  - hexo
  - icarus
  - github.io
categories:
  - hexo
  - icarus
---

## Hexo初始化

> Hexo 是基于node进行安装的

### 必备条件

- Node.js
- Git

<!-- more -->

### 全局安装Hexo

```bash
$ yarn add -g hexo-cli
```

### 初始化hexo目录

```bash
hexo init <文件夹名>

cd <文件夹名>

yarn 
```

### 本地启动服务

```bash
hexo s
```
默认端口`:4000`

### hexo 基础命令

``` bash 
# 清除文件
hexo clean 

# 根据模板生成静态文件
hexo g

# 启动本地服务
hexo s

# 一键部署
hexo d
```
`hexo d` 需要进行一些相关配置，见下文

## 更换主题

个人比较喜欢icarus，这个主题，在当前目录下，输入命令

```bash 
# 将主题文件克隆到 themes 文件夹下
$ git clone https://github.com/ppoffice/hexo-theme-icarus.git themes/icarus
```

修改`_config.yml`文件

``` yml
# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: icarus
```

之后运行命令

```bash
# 如果报错，先运行hexo clean 然后hexo g，重新生成文件
$ hexo s // start a live server
```

## 部署博客

1. github新建一个 repository。repository 应该直接命名为 <你的 GitHub 用户名>.github.io。

2. 安装git部署工具

```bash
yarn add hexo-deployer-git 
```

3. 修改`_config.yml`文件

``` yml
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: <repository url> #git@github.com:<你的 GitHub 用户名>/<你的 GitHub 用户名>.github.io.git
  branch: [branch] #默认master，可不填
  message: [message] #部署时commit信息，可不填
```

4. 一键部署

```bash
hexo d 
```

过几分钟查看`https://<你的 GitHub 用户名>.github.io`，就能看到自己博客啦~