---
layout:     post
title:      android手机作为文件服务器 
subtitle:   基于termux搭建filebrowser 
date:       2019-09-19
author:     Angus 
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - Termux 
    - Android 
    - ssh 
    - filebrowser 
---

> 基于淘汰后的Android手机搭建文件服务器


# 淘汰的andriod手机 
***
  * 中兴z11
  * 内存 6G
  * 存储 128G
  * 挂转转很久无人问津
  * 是否可以他用（文件服务器\博客\是否作为下载器\或者安装docker）
  * root 太麻烦 
# termux 淘汰手机的第二春
***
  * Termux是Android的一个高级的终端模拟器,i
  * 开源且不需要root,支持apt管理软件包，
  * 还支持Python,PHP,Ruby,Go,Nodejs,MySQL等,可玩性很高

  ![官网](https://termux.com/)        
  ![github地址](https://github.com/termux/termux-app)        
  ![google play地址](https://play.google.com/store/apps/details?id=com.termux)        

# termux基本指令
***
Termux除了支持apt命令外,还在此基础上封装了pkg命令,pkg命令向下兼容apt命令.apt命令大家应该都比较熟悉了,这里直接简单的介绍下pkg命令:

* pkg search <query>              搜索包
* pkg install <package>           安装包
* pkg uninstall <package>         卸载包
* pkg reinstall <package>         重新安装包
* pkg update                      更新源
* pkg upgrade                     升级软件包
* pkg list-all                    列出可供安装的所有包
* pkg list-installed              列出已经安装的包
* pkg shoe <package>              显示某个包的详细信息
* pkg files <package>             显示某个包的相关文件夹路径

# termux安装基本攻击
***
* pkg update
* pkg install vim curl wget git unzip unrar
  
  手机没有root
* pkg install proot
  模拟root环境
* termux-chroot 
  如果你手机root
*  pkg install tsu
* tsu 会将用户切换到root下

# filebrowser文件服务器
## 安装
***
   * curl -fsSL https://filebrowser.xyz/get.sh | bash
   * 下载并安装filebrowser
   
## 运行
***
   *  filebrowser -r /data/data/com.termux/files/home/angus
   * 默认是 127.0.0.1:8080
   * 设置 filebrowser config set --address 0.0.0.0
   * 可以通过浏览器访问  ip:8080
   * admin  用户和密码

# 内网穿透
***
  * 使用ngrok或者frp可以将Termux上面搭建的网站映射到外网上去
  * 可玩性更高

