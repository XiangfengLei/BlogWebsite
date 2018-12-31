---
title: 博客工程说明
date: 2018-3-19 19:50:34   
tags: 其他  
categories:  
---
github.com 工程中添加公钥
公钥生成
ssh-keygen  
<!--more-->
下载工程：  
git clone git@github.com:XiangfengLei/BlogProject.git 
 
切换分支：  
git checkout develop 
 
安装hexo：  
npm install hexo-cli -g  
npm install hexo-deployer-git --save
npm install

hexo支持latex数学公式渲染：
1、更改目录下的文件 F:\BlogProject\node_modules\marked\lib\marked.js
其中escape和em两项修改为：
 escape: /^([`*\[\]()# +\-.!_>])/,
 em:/^\*((?:\*\*|[\s\S])+?)\*(?!\*)/,

验证：   
hexo g  
hexo s  
hexo d  (发布前确认CNAME文件是否拷贝到public目录下)  
注： 查看主题目录themes ，如果主题丢失，解压目录下的压缩包，得到主题yilia （目前_config 配置文件中使用的主题）   

git上传工程：  
git status    
git add .   (-u 只更新远程已有的文件)  
git commit -m "上传说明"  
git push  

