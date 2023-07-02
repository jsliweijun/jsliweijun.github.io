---
title: 使用 hexo 搭建个人博客
date: 2016/07/03 10:00:16
updated: 2019/09/15 10:11:17
categories:
    - hexo
tags:
    - 博客
    - hexo
    - md
toc: true
comments: false
---

[hexo](https://hexo.io/zh-cn/) 是一个快速，简洁的博客框架，能方便的搭建起自己的博客系统。

> 1. 它能使用 markdown 写博客文章进行发布展示。
> 2. 它能发布到 GitHub Pages 上。再配合 GitHub Actions 能写好文章提交后，就自动部署发布。
> 3. 它能自定义主题，或者选择丰富的开源主题。

## 1. 搭建 hexo 博客项目

### 1.1. 建站，创建项目

使用 hexo 的 init 命令，创建项目

```js
hexo init jsliweijun.github.io
```

项目文件夹中有如下资源和目录。

```js
.
├── _config.yml   // 博客项目配置文件：网站配置，文章配置
├── package.json  // 项目相关信息，依赖，npm script 命令
├── scaffolds     // 模版文件夹
├── source        // 资源文件夹，用于存放用户资源的地方，创建的博客，博客中使用的images CNAME 配置文件都放这
|   ├── _drafts   // 博客草稿文章
|   └── _posts    // 博客文章
└── themes        // 博客主题资源，自定义主题，或者使用第三方主题都放在这
```

使用命令，本地运行项目

```js
hexo server
```

运行后,会提供一个能本地访问的 [url 链接](http://localhost:4000) 默认是: <http://localhost:4000>

![hexoserver](/images/hexoserver.png)

### 1.2. 认识 hexo 配置，修改部分配置，替换博客主题

先阅读一遍项目的[配置信息介绍](https://hexo.io/zh-cn/docs/configuration) ：<https://hexo.io/zh-cn/docs/configuration>。
然后，动手修改自己项目中的 `_config.yml` 的项目配置， 如

```yml
# Site
title: Oliver's Blog
subtitle: '种一棵树最好的时间是十年前，其次是现在。'
description: '个人博客'
keywords: 个人博客
author: Oliver
language: zh-CN
timezone: 'Asia/Shanghai'
```

访问 hexo 提供的[主题列表](https://hexo.io/themes/)，找一个自己喜欢的主题，下载到本地。
根据[主题文档](https://hexo.io/zh-cn/docs/themes)介绍,将下载到主题，放入到 `theme` 目录下，并修改 `_config.yml` 的配置即可。

```yml
# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
# theme: landscape
theme: quietness
```

不同的主题，修改的配置和需要执行相关的命令也会有所不同，需要看相关主题的文档介绍。

## 2. 将博客发布到 GitHub 上，增加 GitHub Actions 配置

### 2.1. 将博客代码发布上 GitHub 仓库

1.  在 GitHub 上创建仓库。
2.  本地项目 git init 初始化，提交代码。
3.  本地项目关联远程仓库，推送到远程仓库。

### 2.2. 增加 Github Actions 配置

使用[GitHub Actions](https://www.ruanyifeng.com/blog/2019/09/getting-started-with-github-actions.html) 实现持续集成，将我们提交的代码发布，利用 GitHub Pages 提供的功能访问我们的博客。

在项目的根目录下个创建 2 层目录和一个配置文件 deploy.yml : `.github/workflows/deploy.yml`

```yml
name: GitHub Actions Build and Deploy
on: [push]
jobs:
    build-and-deploy:
        runs-on: ubuntu-latest
        steps:
            - name: Checkout
              uses: actions/checkout@master

            - name: Build and Deploy
              uses: jenkey2011/vuepress-deploy@master
              env:
                  ACCESS_TOKEN: ${{ secrets.ACCESS_TOKEN }}
                  TARGET_BRANCH: gh-pages
                  BUILD_SCRIPT: npm install && npm run build
                  BUILD_DIR: public/
```

## 3. 日常使用 hexo 写文章和发布博客的流程

### 3.1. 思考和理清博客文章的大纲

例如写这篇文章时，使用 xmind 列出的大纲

![文章大纲](/images/hexouse.png)

### 3.2 写博客，博客项目管理

使用草稿命令创建草稿文章

```js
hexo new --dragft  <title>
```

创建的文章在 `source/_drafts` 目录下，使用 vscode 编辑器进行文章书写。

本地预览写的文章

```js
hexo server --draft
```

将草稿发布

```js
hexo publish post <title>
```

最后提交文章内容，将其推送到 GitHub 。
