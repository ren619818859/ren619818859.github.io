---
title: Hexo Next-博文分类数和标签数显示有误
date: 2019-04-21 13:56:50
categories: Hexo Next主题Blog搭建心得
---
# 一、首先停止你的网页服务
（1）hexo s启动的服务 ctrl+z关闭
（2）pm2 启动的服务 pm2 stop “你的脚本文件关闭”
# 二、需要移除的文件和文件夹:(不放心可以先备份)
（1）博客根目录下的db.json文件
（2）博客根目录下public目录下的categories和tags文件夹
# 三、重新部署静态博客
```
hexo clean #清除缓存
hexo g     #生成静态网页
hexo s     #启动服务预览
hexo d     #开始部署
```
最后重启网页服务
