# How to draw awesome figures?

本文作者：[Hanlin Cai](https://caihanlin.com/)   [知乎](https://www.zhihu.com/people/chlire)   [B站](https://space.bilibili.com/594030035?spm_id_from=333.1007.0.0)  [Github](https://github.com/GuangLun2000/figure-drawing) 更新时间：2023/03/01

本文分享了我在科技写作（数学建模、科研论文）绘图上的一点心得，并提供了一些可以拿来即用的绘图软件、工具、宏包等等。

一共展示了**六种不同的绘图方案**，每种方案我都附上了基于该方案实现的图例，部分是自制的，部分选自优秀论文。供大家参考！



---

[TOC]

<div style="page-break-after:always"></div>

## 写在最前面

首先要明确的是，美赛国赛等“科技论文”的配图，大致可以分为以下两类：

- 数据图：体现模型的过程数据或结果数据，重点在于“展现模型效果”
- 框架图：描述模型的流程结构或系统组成，重点在于“解释模型本身”

### 1、数据图

- 数据图：体现模型的过程数据或结果数据，重点在于“展现模型效果”
- 根据图形分类：线图、饼图、柱状图、雷达图、地图、三维图、热力图等等
- 根据数据分类：比较类、分布类、流程类、地图类、趋势类、占比类

图1-美赛-2020-A题-鱼群迁徙 #2001334：

<img src="https://p.ipic.vip/o4y56w.png" alt="截屏2023-02-06 17.14.13" style="zoom:33%;" />

图2-美赛-2021-B题-无人机 #2102199：

<img src="https://p.ipic.vip/b2qknp.png" alt="截屏2023-02-06 17.16.15" style="zoom:38%;" />

图3-美赛-2022-A题-自行车运动 #2209812

<img src="https://p.ipic.vip/imbwra.png" alt="截屏2023-03-01 11.41.45" style="zoom:42%;" />

<div style="page-break-after:always"></div>

### 2、框架图

- 框架图：描述模型的流程结构或系统组成，重点在于“解释模型本身”
- 一般分类：思维导图、模型架构图、模型示意图、模型流程图等等

图4-美赛-2020-A题-鱼群迁徙 #2001334：非常著名的建模流程图

<img src="https://p.ipic.vip/kr74z6.png" alt="截屏2023-02-07 21.15.26" style="zoom:28%;" />

图5-2022年国赛-B题-福建省一等奖（自制）

<img src="https://p.ipic.vip/jlyt8s.png" alt="截屏2023-02-06 17.15.12" style="zoom:42%;" />

图6-美赛-2023-B题-重塑马塞马拉 #2316192（自制）

<img src="https://p.ipic.vip/4y23hh.png" alt="截屏2023-03-01 11.38.15" style="zoom:48%;" />

上面两张自制的图片，均使用PPT绘制

<div style="page-break-after:always"></div>

## 方案一、使用 Matlab 绘制“数据图”

- Matlab基本上可以胜任任何“数据图”的绘制，但难以绘制“框架图”；
- **Matlab绘图的逻辑其实非常简单：**
  1. 安装好Matlab
  2. 导入准备好的绘图代码（记得备份）
  3. 导入模型的过程数据
  4. 生成原始图片
  5. 针对需要，对原始图片进一步润色
- 绘图的代码模版 Plot Gallery：https://ww2.mathworks.cn/products/matlab/plot-gallery.html
  - 推荐，阿昆的科研日常，绘图合集：https://www.zhihu.com/column/c_1074615528869531648
  - 同时推荐，MATLAB 特殊绘图：https://www.zhihu.com/column/c_1549339303922057218
- 最后可使用 FigureBest 脚本进行美化，详见： https://www.bilibili.com/video/BV1yP4y1m7H5/

说明：**FigureBest**是b站up主**图通道**制作的一款Matlab图片润色脚本，需要付费使用，好像是¥50左右，有心的话本文提到的所有软件，其实在网上都可以找到相应资源，不过这里不会提供资源渠道。

总而言之，**推荐各位使用正版软件**，至少我自己为这些软件付费了——不仅仅是因为付费可以拥有实时更新的版本与社区，更是出于对知识版权的尊重。当然，如果此刻你还不具备为之付费的能力，没有关系——但当未来你有能力的时候，请予以支持与尊重～

下面展示了 Matlab Plot Gallery 的部分绘图案例，一般而言，搜索任意工具的 Plot Gallery 都可以找到对应的案例大全

![截屏2023-03-01 12.01.06](https://p.ipic.vip/07k8v7.png)



图7-下面是我用 FigureBest 辅助绘制出来的Bar chart，用来展示模型的训练与测试结果（数据对比图），还是比较美观的，推荐熟悉Matlab的选手使用

<img src="https://p.ipic.vip/1cnkgm.jpg" alt="Fig6" style="zoom:33%;" />



**然后是一些使用Matlab绘制的特殊图例，供大家学习借鉴：**

图8-三角曲面图(Trisurf)-出处：https://zhuanlan.zhihu.com/p/590173859

<img src="https://p.ipic.vip/vtahya.png" alt="图片" style="zoom:48%;" />

图9-小提琴图-出处：https://zhuanlan.zhihu.com/p/411001831

<img src="https://p.ipic.vip/eysehx.png" alt="MATLAB 一行代码应用ggtheme主题--violinplot版(小提琴图)" style="zoom:54%;" />



<div style="page-break-after:always"></div>

## 方案二、使用python绘图

- python绘图主要是依赖各种宏包，python和matlab类似，基本上可以实现任何“数据图”的绘制，但无法胜任“框架图”，至于优秀的“框架图”如何绘制，且看方案四和方案五。
- 首先是广受好评的Matplotlib，宏包合集：https://matplotlib.org/stable/gallery/index.html
  - 类似的，Seaborn宏包也非常好，宏包合集：https://seaborn.pydata.org/examples/index.html
  - 可以参考知乎文章，Seaborn画图：https://zhuanlan.zhihu.com/p/81553421
- 另外还有一个汇总合集也非常推荐：[The Python Graph Gallery](https://www.python-graph-gallery.com/)

**下面是一些使用python绘制的图例，供大家学习借鉴：**

Seaborn库可以实现的图片合集-出处在上方已经提供了

<img src="https://p.ipic.vip/khfkit.png" alt="截屏2023-02-07 21.03.16" style="zoom:24%;" />

The Python Graph Gallery-出处在上方提供了

<img src="https://p.ipic.vip/mda3l7.png" alt="截屏2023-02-16 22.24.20" style="zoom:33%;" />

图10-美赛-2023-B题-使用python绘制的结果数据对比图（自制）

<img src="https://p.ipic.vip/95u4np.png" alt="截屏2023-03-01 12.09.12" style="zoom:50%;" />

说明：本文展示的图片仅作实例之用，因此没有提供高清/矢量版本，如需获取原图模版，可以到我的 [Github绘图仓库](https://github.com/GuangLun2000/figure-drawing) 中获取。


<div style="page-break-after:always"></div>

## 方案三、使用$\LaTeX$绘图

- 使用$\LaTeX$画图门槛自然比较高了，就单论画图而言
  - 高效程度：Matlab $\approx $ python$>\LaTeX$
  - 个性化程度：$\LaTeX>$python$>$Matlab
- 但是$\LaTeX$的个性化程度是非常高的，**入门容易高手难**！
- $\LaTeX$绘图大合集：https://awesomerank.github.io/lists/xiaohanyu/awesome-tikz.html
- 推荐项目，Awesome LaTeX drawing：https://github.com/xinychen/awesome-latex-drawing
  - Tikz Gallery 合集：http://leg.ufpr.br/~walmes/Tikz/
  - PGFPlots Gallery 合集：https://pgfplots.sourceforge.net/gallery.html
- 无需配置环境，可以在线使用的$\TeX$编辑器Overleaf：https://cn.overleaf.com/

**这里再提供几份美赛的获奖作品的$\LaTeX$源码：**

- 建议：如果不是三个人都熟悉$\LaTeX$，建模比赛还是使用 Word模版 更加稳妥！
- 2020美赛 D题 O奖：https://levitate-qian.github.io/2020/12/01/latex-lecture/
- 2020美赛 F题 F奖：https://www.latexstudio.net/index/details/index/mid/950.html
- 2020美赛 C题 M奖：https://www.latexstudio.net/index/details/index/mid/963.html

Tikz Gallery 合集-出处在上方提供了

![截屏2023-03-01 12.36.08](https://p.ipic.vip/xjcu9h.png)

图11-使用$\LaTeX$绘图案例-出处 Awesome LaTeX drawing

![drawing](https://p.ipic.vip/ogp4m7.png)

图12-出处 Awesome LaTeX drawing

![drawing](https://p.ipic.vip/gfvklb.png)



<div style="page-break-after:always"></div>

## 方案四、使用亿图图示，ProcessOn等在线软件绘图

- 亿图图示（必须付费）：https://www.edrawmax.cn/online/zh/
  - 数据图，框架图都可以画，特别是“模型总框架图” (our works)
- ProcessOn（基本免费）：https://www.processon.com/
  - 用来画流程图很方便、美观
- Visio（亿图平替）：https://www.office.com/launch/visio?auth=2
- 另外，推荐两个生信学绘图工具
  1. Prism 9：https://www.graphpad.com/updates/prism-950-release-notes
  2. Bioladder：https://www.bioladder.cn/web/#/pro/index


说明：软件的方案有很多种，最推荐的是**亿图图示**，虽然需要付费，但是模版素材丰富，很多O奖论文也都是采用这款软件进行图片绘制（比如浩然同学、清风数学建模的视频）；而ProcessOn提供学生免费使用的次数，很良心；Visio是微软的365软件全家桶之一，社区也比较丰富，基本上可以说是亿图图示的平替。Prism 9和Bioladder这两个软件，主要用于环境科学、生物科学类的赛题。

再次说明：本文提到的所有软件，其实有心的话，网上都可以找到资源。当然希望大家有能力的话，请支持正版！

图-2022美赛-E题-森林固碳 #2220714

<img src="https://p.ipic.vip/qsd1rf.png" alt="截屏2023-02-07 21.09.47" style="zoom:30%;" />

图3回顾-美赛2020A题-鱼群迁徙 #2001334 —— 非常出名的一篇文章

<img src="https://p.ipic.vip/kr74z6.png" alt="截屏2023-02-07 21.15.26" style="zoom:28%;" />

图-美赛-2021-B题-无人机 #2102199：

<img src="https://p.ipic.vip/5b3msn.png" alt="截屏2023-02-07 21.17.37" style="zoom:48%;" />

图-美赛2022年A题-自行车功率 #2209812 “对上图的模仿”

<img src="https://p.ipic.vip/zz1gl0.png" alt="截屏2023-02-07 21.19.14" style="zoom:33%;" />





<div style="page-break-after:always"></div>

## 方案五、使用PPT绘图

- 首先需要说明的是，大部分同学都低估了PPT的能力，其实用好Office三件套，能达到非常强大的效果！
- PPT最主要的应用场景：
  - 绘制几何题：2D、3D、几何图形、空间图形绘制
  - 给图片润色：其他方案绘制好图片之后，使用PPT对其添加文字、箭头等“矢量修改”
- 一个非常棒的教学视频：[数模美赛冠名O奖学长教你论文插图制作](https://www.bilibili.com/video/BV1c5411W7U9/)

以下是我在2022年FZU校内比赛和2022国赛绘制的图片合集，**离散题/几何题**主要都是使用PPT实现：

图-交通枢纽最优布局问题：

<img src="https://p.ipic.vip/rd26v7.png" alt="离散合集1" style="zoom:32%;" />

图-2022年国赛B题（省一）无人机编队飞行示意图：

<img src="https://p.ipic.vip/q88yho.png" alt="离散合集2" style="zoom:26%;" />

<div style="page-break-after:always"></div>

## 方案六、使用Javascript进行数据可视化

- 这里再提供一种新颖的思路，使用js来进行可视化，主要用于绘制“数据图”。是不是简单问题复杂化，就因人而异了，如果队伍里有擅长前端程序的同学，可以考虑这种思路。
- Apache ECharts，一个基于 JavaScript 的开源可视化图表库：https://echarts.apache.org/zh/index.html
  - pyecharts-gallery：https://gallery.pyecharts.org/#/

- AntV team，蚂蚁集团的数据可视化项目，https://github.com/antvis/

![截屏2023-03-01 11.37.54](https://p.ipic.vip/3w3mnm.png)



<div style="page-break-after:always"></div>

## 学习绘图路上，对我帮助很大的博主们：

- 全网最好的数学建模课程之一：[数学建模清风——论文排版教程](数学建模清风——论文排版教程)
- 2020年美赛D题**O奖得主**，@Levitate_同学：[10类案例带你了解论文插图制作](https://levitate-qian.github.io/2020/05/04/10%E7%B1%BB%E6%A1%88%E4%BE%8B%E5%B8%A6%E4%BD%A0%E4%BA%86%E8%A7%A3%E8%AE%BA%E6%96%87%E6%8F%92%E5%9B%BE%E5%88%B6%E4%BD%9C/)
- 2021年美赛B题**O奖得主**，@b站浩然同学：[O奖干货分享]( https://www.bilibili.com/video/BV1eP411F7Ny/?share_source=copy_web&vd_source=c8936a3bacfd65375f9e88b3bb9a12ba)
- 2021年美赛D题**F奖得主**，@b站师翊同学：[超简单的美赛D题的MATLAB求解](https://www.bilibili.com/video/BV1we4y1g7MM/)







<div style="page-break-after:always"></div>

## 最后，数学建模优秀绘图案例欣赏

**多看多练，模仿是最高效的学习方式！**

图-来源-[Yi Zhu的出版物](https://bryanyzhu.github.io/publications/)

<img src="https://p.ipic.vip/90awzs.png" alt="comus" style="zoom:33%;" />

<img src="https://p.ipic.vip/1c9sj0.png" alt="impdet" style="zoom: 50%;" />

<img src="https://p.ipic.vip/p330i4.png" alt="pipeline-v7" style="zoom:33%;" />



