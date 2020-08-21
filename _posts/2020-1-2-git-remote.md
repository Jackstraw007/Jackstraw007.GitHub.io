---
layout: post
title: github远程配置
author: Jeniac
categories: [Jekyll Paper]
date: 2020-1-2
---

# Github is great!

tips：

git添加远程库用```Clone with SSH - Use a password protected SSH key.```就不会每次要求输入密码

看了好多资料终于搞定了git 中clone命令报错这个问题，废话不多说直接上步骤希望对大家有帮助。

1   删除.ssh文件夹（直接搜索该文件夹）下的known_hosts(手动删除即可，不需要git）

2   在下载好的Git中的bin目录下打开bash.exe输入命令ssh-keygen -t rsa -C "username" (注：username为你git上的用户名)，如果执行成功。返回：

Generating public/private rsa key pair.
Enter file in which to save the key (/Users/username/.ssh/id_rsa): //这里的username是电脑上的用户名，这个地址也是文件的存储地址，然后我们按

回车，如果你以前有存储地址会返回/Users/your username/.ssh/id_rsa already exists.Overwrite (y/n)?直接输入y回车。如果以前没有储存地址就会出现

Enter passphrase(empty for no passphrase);也直接回车，两种情况回车后都会出现 Enter same passphrase again 然后接着回车会显示一长串内容其中

还有一些..o.. o oo .oS. 之类的代码，这说明SSH key就已经生成了。文件目录就是：username/.ssh/id_rsa.pub.

 

3  然后找到系统自动在.ssh文件夹下生成两个文件，id_rsa和id_rsa.pub，用记事本打开id_rsa.pub将全部的内容复制。

4  打开https://github.com/，登陆你的账户，进入设置（Settings）找到 New SSH Keys

5  然后将你复制的内容粘贴到key中

    再点击Add SSH Key                     

    ok还有最后一步

6  仍然在bash.exe中输入ssh -T git@github.com然后会跳出一堆内容你只需输入yes回车就完事了，然后他会提示你成功了。

    然后你就可以正常使用git clone命令了，最后祝你好运哈哈！
