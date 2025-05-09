---
title: git命令简记
date: 2024-03-30 13:04:49
tags: git
categories: 技术
---
# 情况说明：

昨天晚上，在2个小时的debug之后，我终于成功重构了我的数据处理程序，让它看起来没那么简陋了。下一步的工作是更新github上的repo，之前使用过git来提交我的博客文章，所以这次我决定也使用git来提交我的代码。嗯，没得说，又是一个多小时的折腾，经过与gpt来来回回的反复扯皮，我终于是搞清楚了git的几个简单命令，现在我要把它们记录在册，免得下次使用还是记不得

# 使用git上传本地代码到github上的简单方法

### 第一步，cmd导航到对应的文件夹

可以使用cd命令一个文件夹一个文件夹地找过去，也可以直接cd #文件路径直接找到目标文件夹。注意，切换盘符时不使用cd命令，直接输入对应的盘符即可。比如从C盘切换到D盘，输入D:即可

### 第二步，绑定ssh密钥

这一步因为我之前上传博客文章的时候已经做过，所以掠过。注意，git不仅支持ssh绑定，也可以输入仓库的url，只是这样每次传文件的时候都需要登录github(输入账号密码)

### 第三步，初始化git仓库，命令：git init

这一步将你的本地代码文件夹变成了本地代码仓库

### 第四步，添加文件到本地仓库：git add .

git add是添加文件命令， .表示添加文件夹内全部代码，你也可以指定添加的文件路径

### 第五步，查看本地分支，命令：git branch

由于github在2020年做了一次更新，所有repo的默认主分支从master改成了main，而git并没有追随这一改动，造成了本地主分支名和远程仓库主分支名不一致，所以需要查看本地主分支名。如果不一致则需要修改

### 第六步，修改本地分支名，命令：git branch -m master main

这一步将主分支从master重命名到main

### 第七步，添加远程仓库，命令：git remote add origin [git@github.com](mailto:git@github.com):username/repo.git

这里的username和repo分别是你的github用户名和仓库名。origin是你本地仓库的命名，习惯上用origin，你也可以指定其他的名字

### 第八步，将本地分支推送到远程仓库，命令：git push -u origin main

这个命令会将本地的分支推送到远程仓库的分支中，并在远程仓库中创建与本地分支同名的分支。注意，如果远程仓库中已经存在该分支，该命令会提示推送失败。
