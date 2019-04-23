---
title: Hexo Next-1 GitHub+linux+hexo
categories: Hexo Next主题Blog搭建心得
---
# 前言
<table><tr><td><font size=3> 本文主要讲解
    <li>Hexo在Linux环境下的部署
    <li>Linux上部署的Hexo备份到GitHub
    <li>基于Next主题优化Hexo
</li></font></td></tr></table>

这是我的博客网站：
GitHub：https://ren619818859.github.io  
阿里云：http://www.rlovey.fun/

# Hexo在linux环境下的部署
## Hexo介绍
Hexo是基于NodeJs的静态博客框架，简单、轻量，其生成的静态网页可以**托管在Github**和Heroku上。

- 超快速度
- 支持MarkDown
- 一键部署
- 丰富的插件

## 环境的准备
### 安装node.js
去[nodejs官网](https://nodejs.org/en/download/)下载对应系统的安装包安装。
检验安装成功
```
node -v
```
### 安装hexo
```
npm install hexo-cli -g
```
这里如果安装失败，则需要配置环境npm的环境变量如下：
```
ln -s /“你的node.js文件夹/bin/”
```
## 利用Hexo搭建一个博客
---------------------------------
# Linux上部署的Hexo备份到GitHub
## 首先我们得申请一个GitHub
进入[GitHub官网](https://github.com/)
![github申请账号](../Hexo-Next-view-tags-and-categories/username.png)
** 注意：如果你不想买域名的话，以后此博客的域名类似于你申请的账号也就是uesrname **
邮箱验证很简单
## GitHub博客仓库的建立
点击右上角的New repository 如图:
![pic-1](../Hexo-Next-view-tags-and-categories/p-1.png)
注意仓库名称一定是你的**用户名.github.io** 具体操作如图：
![pic-2](../Hexo-Next-view-tags-and-categories/p-2.png)
## 关联GitHub远程和本地仓库
- 设置Git的用户名和email
```
git config --global user.name "你的Github用户名"
git config --global user.email "你注册Github使用的邮箱"
```
- 生成ssh密钥 //原因自行百度
```
ssh-keygen -t rsa -C "你注册Github使用的邮箱"
```
找到生成的ssh密钥，复制其中全部内容到如图位置下：
![pic-3](../Hexo-Next-view-tags-and-categories/p-3.png)
![pic-4](../Hexo-Next-view-tags-and-categories/p-4.png)
## 配置Deploy
vim博客站点_config.yml文件，找到deploy，修改为
```
deploy:
  type: git
  repo: https://github.com/用户名/用户名.github.io.git
  branch: master
```
## 开始部署
```
hexo g //生成加载页面
npm install --save hexo-deployer-git  //部署git
hexo d //部署hexo
```
期间会提示输入你的GitHub账户和密码
至此，hexo已经在github上备份完毕，blog也可以浏览
# 基于Next主题优化Hexo
未完待续

