---
title: "Linux 学习笔记"
pubDate: "2023-12-20"
description: "在寒假开始之前开始了Linux的学习~~~一点一点记录吧~~"
heroImage: "https://imgcdn.hope-blog.top/2023-12-20/01.bmp" 
tags: ["Linux 学习笔记"]
---

### 前置准备
Linux是一个操作系统，而操作系统，是调度电脑的软件和硬件的核心部件。

##### 配置虚拟机环境
由于个人电脑都是已经有固定的操作系统，常见的有 windows 或者 mac ，那么我们就需要在现有的操作系统上搭建一个虚拟的电脑环境来执行Linux上的功能。当然，已经有很多公司帮你做好了这样的软件，你只需要选择下载一款比较满意的软件去执行就好。

我使用的是[VMware Workstation](https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html)

##### 远程控制虚拟机
由于跨系统操作的很多不便，我们可以使用远程软件连接我们的虚拟机，在电脑原有的操作系统上对虚拟机进行修改，如此便可以很方便地使用原有操作系统中的文件啦。

我使用的是[FinalShell](http://www.hostbuf.com/downloads/finalshell_install.exe)

接下来就是连接虚拟机后做测试啦，测试完成后就可以开始正式的操作了！congratulations!

### 基础操作指令

首先要知道，命令由三部分组成：command [-options] [parameter]

其中，command 是基本命令本身，options是可选行为细节，paramater是可选命令指向的参数（中括号代表可选）

+ ls -a -l -h
ls可以访问目录，选择-a可以查看所有文件，包括隐藏文件，-l可以纵向排列文件，并显示详细信息，-lh可以列出文件大小（主要是显示单位）

指令和参数都可以混合使用
``` bash
ls -al        
ls -la
ls -a -l       //三者都是表示al同时执行 ，即纵向显示所有文件
ls -alh        //显示所有文件的同时详细展示内存大小
ls -alh /      //显示所有文件的同时详细展示内存大小后回到根目录
```
+ cd
cd （change direction）表示转换当前目录，后面不加参数就默认回到home。cd后面有两种形式描述路径，一种是绝对路径，从根目录开始写，第二种是相对路径，从当前路径下寻找。

``` bash
cd /home/Desktop
cd Desktop
```

+ pwd
pwd（print working direction）打印当前工作路径。

+ 特殊路径符

``` bash
cd .                  //'.'表示当前目录
cd ./Desktop          //表示转向当前目录下的Desktop文件
cd ..                 //'..'表示退回上一级目录
cd ../..              //'../..'表示退回上两级目录
cd ~                  //'~'表示HOME目录
cd ~/Desktop
```

+ mkdir
mkdir(make direction),创建新文件夹

``` bash
mkdir test          //在当前目录（HOME）下创建文件夹test
cd ~                //回到HOME
ls                  //展示HOME下的文件，此时会显示test

mkdir -p itcast/text2/good    //多级建立文件夹
cd itcast
ls                 //展示itcast中是否有text2这个文件夹

```

+ touch + 路径
用于创建一个新的文件（attention ，是文件不是文件夹）

+ cat + 路径
用于查看文件内容（全部展示）

+ more + 路径
（对于内容很多的文件）用于查看文件内容（翻页展示）



``` bash
ls                       //展示当前目录文件
touch text.txt           //创建文本文件
ls -l                    //展示当前文件目录（d开头dictionary的是文件夹，-开头的是文件）

//创建好文件之后，在图形化界面在文件中加入一些内容

cat text.txt             //显示文件内容
more /etc/services       //按空格翻页，按q退出

```
+ root用户（超级管理员）
``` bash
su - root          //进入超级管理员验证，输入开机密码

exit               //操作完成后退出管理员身份
```


+ 通配符
``` bash
text*         //表示所有以text开头的文件
*text         //表示所有以text结尾的文件
*text*        //表示所有包含text的文件

```

+ cp
cp(copy)可以复制一个文件（夹）的内容到另一个文件（夹）中。对文件夹进行操作时要加-r。

+ mv
mv(move)可以将一个文件（文件夹）换位置到其他目录下。或者可以实现重命名。

+ rm 
rm(remove)删除文件（文件夹）。对文件夹进行操作时要加-r。可以同时对多个文件同时进行删除。





``` bash
ls
cp text.txt text2.txt           //将text.txt的内容复制到text2.txt中
cat text.txt
cat text2.txt                   //分别展示两个文件的内容，结果应该是一样的
cp -r itroy itroy2              //复制文件夹要使用-r

mv text.txt Desktop/            //将文件移动到Desktop目录下
ls Desktop/                     //展示Desktop目录下的文件
mv text2.txt text3.txt          //text3.txt文件不存在，默认将text2.txt更名为text3.txt
ls                              //展示文件，text2.txt消失了，而text3.txt存在该目录下，内容不变

re text3.txt                    //删除text3.txt
rm -r itcast itroy text         //同时删除后面的文件

```

+ which
查找命令的程序文件

+ find
查找指定文件 find （起始目录） 查找方式 要求
两种方式：按文件名查找；按文件大小查找

``` bash
which cd
which pwd
which mkdir
which re          //输出这些程序的存放地址

find / -name "*test"     //按文件名搜索
find / -size +100M       //按大小搜索，+100M表示大于100M的文件
find / -size -10K       //小于10K的文件
find /usr -size +100M   //从ust这个目录开始找
```

+ grep 
从文件中通过关键字过滤文件行
语法：grep -n 关键字 文件路径

+ wc
统计文件的行数、单词数量、字节数（所占内存）

``` bash
grep -n "hello" test.txt      //筛选含有hello关键字的行

wc test.txt                   //输出文件的行数、单词数量、字节数
wc -c test.txt                //输出字节数
wc -m test.txt                //输出字符数量
wc -l test.tst                //输出行数
wc -w test.txt                //输出单词数量

```

+ 管道符 |
管道符可以将左操作结果作为右操作的输入，最后输出右操作的结果。

``` bash
cat test.txt | grep "hello"    //将左边的结果test的输出结果作为右边grep的文件路径
cat test.txt | wc              //将左边的结果test的输出结果作为右边wc的文件路径
ls | grep "test"               //筛选当前目录下文件名中包含test的文件

ls -l /usr/bin | wc -l          //左操作将/usr/bin下的所有文件按行排列，一个文件占用一行，右边统计行数，就可以输出这个目录下文件的总数

cat test.txt | grep "hello" |grep "roy"        //管道符可以嵌套使用，其操作时左结合的。

```

+ echo
echo可以输出指定的内容

+ >  >>
重定义符，> 将左侧命令结果覆盖写入右侧文件中；>>将左侧结果追加写入右侧文件中。

+ tail 
查看尾部文件，可以持续追踪。
语法：tail [-f -num] 路径

``` bash
echo "hello world, im Linux"
echo `pwd`                          //``反引号符，输出pwd的结果而不是输出pwd

echo "hello xixi" >> test.txt       //在原有内容上追加
echo "all change" > test.txt        //覆盖原有内容

tail test.txt                      //从尾部开始输出，默认10行
tail -5 test.txt                   //从尾部开输出5行
tail -f test.txt                   //追踪当前的变化（可以复制一个操作页面，对test文件做修改，当前文件会实时显示，使用Ctrl C结束追踪）

```
+ vim
vim 编辑器可以对文本内容进行编辑。vim总共有三种模式，键入vim默认进入命令模式，键盘的输入都会被视作快捷键，输入i可以就进入输入模式，从键盘上读取的视作修改。按Esc退出命令模式。还有一种底线命令模式。

``` bash
vim hello.txt           //若文件存在则对文件进行修改，不存在就创建一个新文件并对其进行修改

//进入后按i，即可进行修改

//修改完成后，键盘输入：wq，：已经进入底线命令模式，w-保存，q-退出。

cat hello.txt           //在主操作页面中可以查看修改后的内容。


```



