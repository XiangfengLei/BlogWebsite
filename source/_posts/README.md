---
title: 博客工程说明
date: 2018-3-19 19:50:34   
tags: BlogSpace  
categories:  
- other

---
github.com 工程中添加公钥
公钥生成
ssh-keygen  
<!--more-->
下载工程：  
git clone git@github.com:XiangfengLei/Website.git 
 
切换分支：  
git checkout develop 
 
注： 
master 分支是由hexo d发布develop分支内容到master。
develop 分支是用来编写文档、搭建hexo环境、发布网页

安装hexo：  
npm install hexo-cli -g  
npm install hexo-deployer-git --save
npm install
npm uninstall hexo-renderer-marked --save
npm install hexo-renderer-kramed --save

hexo支持latex数学公式渲染：
1、更改目录下的文件node_modules\kramed\lib\rules\inline.js  
//  escape: /^\\([\\`*{}\[\]()#$+\-.!_>])/,

 escape: /^\\([`*\[\]()#$+\-.!_>])/
  
//  em: /^\b_((?:__|[\s\S])+?)_\b|^\*((?:\*\*|[\s\S])+?)\*(?!\*)/,  
 em: /^\*((?:\*\*|[\s\S])+?)\*(?!\*)/

解压主题themes yilia

验证：   
hexo g  
hexo s  
hexo d  (发布前确认CNAME文件是否拷贝到public目录下)  
注： 查看主题目录themes ，如果主题丢失，解压目录下的压缩包，得到主题yilia （目前_config 配置文件中使用的主题）   

问题：
如果出现hexo g 错误则按提示：
npm install hexo

如果hexo d 成功，且hexo s正常，网页出现404节目，则删除node_modules，然后重新进行安装hexo。

使用markdownpad2插入图片

![](https://i.imgur.com/O0rhha5.jpg)

