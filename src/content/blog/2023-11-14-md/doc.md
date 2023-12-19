---
title: "个人博客的建立流程"
pubDate: "2023-11-14"
description: "关于个人博客的建立的笔记"
heroImage: "http://localhost:4321/@fs/D:/code/Hope-second-try/src/theme-simple/assets/media/11.jpg?origWidth=2176&origHeight=1224&origFormat=jpg"
tags: ["web"]
---

# 个人博客的建立流程
本篇博客主要用于回顾和记录个人博客的建立流程，因为涉及到很多重要的步骤，为了防止自己遗忘相关的操作，会详细地记录过程以及一些容易犯的错误（没错，因为本人犯过很多很愚蠢的错误）。本篇文章的目的就是教会像不久前的我一样的小白可以大致理解整个过程。

## 工具介绍
在开始介绍流程之前，我想有个工具是你必须要知道的。
    
+ [Github](https://github.com)
关于Github，百度百科给出的定义是：
>GitHub 是一个面向开源及私有软件项目的托管平台，因为只支持 Git 作为唯一的版本库格式进行托管，故名 GitHub。简单说，GitHub就是一个源代码版本管理工具。
    
由于它的开源性，使得我们可以在其中获取开源代码，甚至于一些高校会将自身的课程资源放入Github，所以，如果你像我一样只是一个学生，也许你可以从查找这些资源开始你的Github之旅。很自然的想法是，我们可以在Github上找到优秀的程序员写好的个人博客代码，将其变成自己的博客。我就是这么干的，这个博客的源代码来自一位优秀的程序员[itmowang](https://github.com/itmowang)，你可以在Github上找到他和他的作品。
那么如果你要使用github，你必须配备git，在官网上下载即可。

+ [nodejs](https://nodejs.org/en)

## 流程介绍
喔吼下面开始流程吧~

### step one 在 Github 上拉取项目

#### clone
书接上文，我们需要从Github上拉取我们心仪的项目
[Github入口](https://github.com/itmowang/sxq-astro)
![Github入口](http://img.blog.loli.wang/2023-11-6-astrosetup/01.png)
点击第一项“Create a new repository”进入后，填写你的项目名字(在这一步，最好将你的项目名字命名为ID.github.io，这样你就可以使用github赠送给你的域名)和描述，成功创建之后，你就可以在你的仓库中找到这个项目。

#### recheck 这一步用于检测项目的克隆是否成功
![查看入口](D:\code\Hope-second-try\src\content\blog\2023-11-14-md\11.bmp)
如果在你的首页看到了你刚刚创建的项目，说明上一步已经成功了。如果没有，说明的你的上一步出现了一些问题，请返回重新开始~~~

#### pull

打开你的命令提示符，进入D盘（建议放在D盘）

``` bash
:d
cd (你想存放的地址)
git clone https
```

![上面的网址来源](D:\code\Hope-second-try\src\content\blog\2023-11-14-md\22.bmp)
上面的步骤也许需要重复很多次，发生错误的话请保持网络稳定多试几遍
``` bash
//进入你存放文件的地址
pnpm i
pnpm dev
```
pnpm dev可以告诉你你的网址，复制网址进入浏览器打开，就可以看到网站的界面。恭喜你已经成功了一大半了。

如果没有成功，你需要检查：
+ 克隆是否成功
+ 是否已经进入存放文件的地址

### step two 修改网站相关信息
网站的修改是由你自己决定的，你可以试试删除一些测试文章，或者创建一个test文章。这一步是为了测试，并方便下面的上传测试。

### step three 上传

#### 本地测试
在上传之前，我们最好在本地测试一下效果，口令和操作也很简单。
``` bash
//进入你存放文件的地址
pnpm dev
```
复制网址进入，你就可以看到修改后的样子，如果有不满意的地方就回到编辑器继续修改。
如果发现没有修改？你需要检查：
+ 在编辑器中是否保存？
+ 文本格式或者图片格式是否正确？

#### 上传
进入命令提示符
``` bash
//进入你存放文件的地址
git init
git add .
git commit -m "name"
git push
```
这就是最后一步了，也是需要耐心，保持网络的稳定，上传成功就快去你的网站上看看吧~~~
如果没有成功，你需要检查：
+ 克隆是否成功
+ 指令是否出错(注意空格和英文点)

### finish! 完成啦！开始你的博客之旅吧！

