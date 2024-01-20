---
title: "[数模基础]chapter1——离散数学建模"
pubDate: "2024-01-15"
description: "开启~"
heroImage: "http://localhost:4321/@fs/D:/code/Hope-second-try/src/theme-simple/assets/media/11.jpg?origWidth=2176&origHeight=1224&origFormat=jpg" 
tags: ["数模"]
---


### 工具介绍
常用的工具有很多，课程推荐的是MATLAB这个软件，是MATWORLD公司开发的建模软件，和很多高校有合作，我们学校开设的者们课程就是和MATWORLD公司合作的，所以会提供很多教程和证书权限。MATLAB的下载可以使用官方网页下载，也可以使用学校资源进行下载。

下面是MATLAB入门课程 ，通过不到两个小时的课程就可以基本了解MATLAB使用方法。
![MATLAB入门指南]https://matlabacademy.mathworks.com/cn/details/matlab-onramp/gettingstarted

### 目录
+ 线性规划模型——一维切割问题
+ 图像处理
+ 空间距离- K聚类方法




#### 空间距离- K聚类方法
“两个总体”选取k聚类的方法
（1）随机取k个元素，作为k个簇的中心.
（2）利用k个簇的中心,将所有元素聚类.
（3）根据聚类结果，计算k个簇各自的中心.
（4）将全部样本元素,按新的中心重新聚类.
（5）重复步骤2-4，直到聚类结果不再变化.

案例：蠓虫聚类与识别、鸢尾花聚类与识别

``` bash
问题：上面附件是 Fisher 鸢尾花数据，包括 145 个鸢尾花标本的萼片长度、萼片宽度数值，请用 k 均值聚类算法分为三簇，再用欧式最小距离方法判断下面数据点属于哪一类：(5.3, 3.7)、(5.0, 3.3)、(5.1, 2.5)、(5.7, 2.8)、(5.9, 3.0)。
format bank; % 保留结果显示为包含两位小数点

% 原始数据
Af = data(:,:); 
figure;
plot(Af(:,1),Af(:,2),'k*','MarkerSize',8);
title '鸢尾花原始数据';
xlabel '萼片长度'; 
ylabel '萼片宽度';

% 聚类计算
rng(1); % For reproducibility 目的是为了结果的可重复性
[idx,C] = kmeans(Af,3)



% 可视化聚类结果
figure;
gscatter(Af(:,1),Af(:,2),idx,'brg')
hold on
plot(C(:,1),C(:,2),'kx', 'MarkerSize',15,'LineWidth',3)
legend('Af','Apf','Atf','质心')
title '鸢尾花数据聚类结果';
xlabel '萼片长度'; 
ylabel '萼片宽度';

% 预测
Xtest = [ 5.3, 3.7 ; 5.0, 3.3 ; 5.1, 2.5 ; 5.7, 2.8 ; 5.9, 3.0]; % 测试数据
[~,idx_test] = pdist2(C,Xtest,'euclidean','Smallest',1) % 计算距离每个测试数据点最近的质心


% 可视化预测结果
gscatter(Xtest(:,1),Xtest(:,2),idx_test,'brg','oo')
legend('Af','Apf','Atf','质心','属于Atf的测试点')
title '鸢尾花数据预测结果';
xlabel '萼片长度'; 
ylabel '萼片宽度';

```
![](https://imgcdn.hope-blog.top/2024-1-15/01.png)
使用下来，我觉得MATLAB最大的优点就是图像的反馈很清晰，使用很简便，属于初学者很好上手的一类工具，用这些工具来解决这些问题现得比较轻松。








