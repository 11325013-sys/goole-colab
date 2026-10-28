Google Colab 部署自己的机器学习项目

CaoChengtai

墨衍会员
·
AI 创作全网分发
码龄10年
关注
原创
2019-07-03 23:24:04
6.6k 阅读
AI 写同款
·
数据监测
›
在Google Colab中无缝集成VS Code：提升开发效率的完整指南
本文详细介绍了如何在Google Colab中无缝集成VS Code，显著提升开发效率。通过安装ColabCode包和配置VS Code服务器，开发者可以享受智能补全、断点调试等高级功能，同时优化文件管理和项目实战流程。特别适合机器学习和小型项目开发，实现云端与本地开发体验的完美结合。
阅读详情
1. 介绍
Google Colab 提供的是免费Tesla K80 GPU，可以玩Keras、Tensorflow、PyTorch或者Mxnet等。Tesla K80还是一块比较高性能的GPU。主要是免费，免费，免费 ！！！ 好像这次真的薅资本主义羊毛了，个人试了几天，感觉还不错。刚入手的时候稍微有点麻烦，大部分的网上教程都是在 Colab 上手动写代码玩玩儿，但是我是自己在本地写好了一个小的项目，然后相互之间 import 有点麻烦，最后自己摸索总结出了一套最简单的上传自己项目，用 colab 跑出结果的方法。

2.准备工作
谷歌一系列，所以先得出去
注册一个谷歌账号
用自己的谷歌账号使用 google driver
自己的项目在本地调试通过，放在一个文件夹里面（包含数据集，最好是英文名字）
3.步骤
3.1 进入 google driver：https://drive.google.com
3.2 右键上传项目 所在的文件夹：

https://i-blog.csdnimg.cn/blog_migrate/09e3e7b3f4f97f13f0683c6262b061cf.png
https://i-blog.csdnimg.cn/blog_migrate/6d5b17a2434dfaf201c8937f640859ae.png
https://i-blog.csdnimg.cn/blog_migrate/4d37927a4ededb77836a7e92e4dfbcb0.png
https://i-blog.csdnimg.cn/blog_migrate/50e94fca8deab91da2924ed5be31a3e5.png
![在这里插入图片描述](https://img-blog .csdnimg.cn/20190703225625905.png
我这里简单地上传了一个名为 test  的文件夹，里面只有一个 main.py 的文件，代码也很简单，但是可以简单测试 Pytorch 的使用。

3.3 进入 colab：点击左上角 “新建” --> “更多” --> “Colaboratory”
https://i-blog.csdnimg.cn/blog_migrate/f59910d800495b82f1ffaab500684cd2.png
https://i-blog.csdnimg.cn/blog_migrate/222b76b007840e17626fccf7a9c14148.png
https://i-blog.csdnimg.cn/blog_migrate/69a3755864c781d7925077f592e459ea.png
3.4 “Edit ” --> “Notebook settings” -->

这里我选择的 Python3 （根据自己代码依赖的环境） 和 GPU，如果要用 GPU 这一步必须调整好。每次调整这里的设置，后面的步骤都要再次进行。所以推荐这里设置好
https://i-blog.csdnimg.cn/blog_migrate/3a80f36e25f695c5b0b609ed8c8d9d0f.png

3.5 代码段里面输入
from google.colab import drive
drive.mount(’/content/drive/’)

然后点击左侧的运行图标，或者 Ctrl + Enter 运行。这时候会出现
https://i-blog.csdnimg.cn/blog_migrate/eb5ac56afd818107cf050f7016002093.png
点击 URL 进入，授权 Google 用户，然后复制授权码粘贴到输入框，Enter。这个时候回显示挂载成功
https://i-blog.csdnimg.cn/blog_migrate/01b60cadbe84173e74bdef52741cce6d.png
这里可以输入

!ls
https://i-blog.csdnimg.cn/blog_migrate/1aedb667ab2b749e33cbb4acac924496.png

可以看到此目录下文件。

3.6 代码段里面输入
import os
os.chdir(“drive/My Drive/test”)

最后一个 test 是其实是自己的项目名。这个时候没有任何提示信息，因为是 Linux 内核，所以按照 Linux 的思想：没有消息就是最好的消息。说明一切顺利。
这里可以输入

!ls


可以看到我们写的 main .py 文件。

3.7 代码段里面输入
!python main.py


成功搞定~

4 注意事项
虽然是 Linux 内核，但是每次类似于 Linux 的语句之前要多一个 “!” 。比如步骤 3.6， 3.7
步骤 3.6 第二个语句最后一个路径名称根据自己上传到 Google Driver 的文件夹的名字而定，我上传的是 “test ”，所以最后一个路径是“test”。
收录于

杂货店

天工造物局
标签
#Google Colab
#Google Driver
#Pytorch
版权声明：本文为博主原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接和本声明。
Colab隐藏玩法：用VS Code直接编辑云笔记本的保姆级教程
本文详细介绍了如何在Colab云端实例上通过colabcode工具运行完整的VS Code环境，实现云端开发体验的全面升级。从环境准备、核心组件安装到深度定制和实战演示，帮助开发者高效利用Colab的GPU资源和VS Code的专业编辑功能，提升机器学习项目的开发效率。
阅读详情
相关推荐
换一换
Python 3与TensorFlow 2的机器学习实战

本文深入探讨了使用Python 3和TensorFlow 2进行机器学习的基础知识与高级技巧，包括了代码示例、谷歌Colab的使用、以及利用云平台进行深度学习的方法。通过实例演示了如何在Google Colab中利用免费GPU资源进行模型训练，并介绍了Google Cloud Platform作为机器学习的强大后盾。

weixin_32311823的博客
395
LLMs-入门二：基于google云端Colab部署Llama 2

由于不是所有GPU都支持深度计算（大部分的Macbook自带的显卡都不支持），同时显卡配置的高低也决定了计算力的大小，因此Colab最大的优势在于我们可以“借用”谷歌免费提供的GPU来进行深度学习。注：如果使用Colab没有购买硬件加速器，而使用免费的T4 GPU，在安装到该步骤后大概率会出现内存崩溃的情况。如果想继续使用，需要想办法购买Colab方案才可以。Colab提供5种硬件加速器，如果需要使用A100GPU、V100GPU需要单独付费，其他类型的硬件加速器效果不是很理想，适合的Colab方案如下。

Josong的博客
3707
Gröbner基方法入门第I部分:项序和约化

Gröbner基方法入门第I部分:项序和约化 理想的准素分解与矩阵分解是计算代数的核心问题,它们在计算机代数、计算代数几何、代数编码和密码学、多维系统理论等学科都有非常重要的理论意义与应用价值.Gröbner基理论是研究理想的准素分解与矩阵素分解的重要工具之一.更简单地概括:Gröbner基方法是从任意一个多项式理想的一组给定生成元,计算另一组性质良好的生成元,并称为该理想的Gröbner基.它能用来判定任意多项式是否属于该理想. Gröbner基的代数算法是Buchberger在1960年代开发的,并

MinCong Luo的博客
4248
太强了！LIama 3.1正式发布

Datawhale干货编辑：量子位、Datawhale刚刚，LIama 3.1正式发布，登上大模型王座！在150多个基准测试集中，405B版本的表现追平甚至超越了现有SOTA模型GPT-4o和Claude 3.5 Sonnet。也就是说，这次，最强开源模型即最强模型。各大云厂商也在第一时间上线了的Llama 3.1的支持，价格是酱婶的：LIama 3.1官方正式发布首先来看模型能力。Llama...

Datawhale
647
yersinia -G打不开图形化界面解决方案（曲线救国，实操可行）

附Kali 2021 VMware懒人版，已完成汉化，更新源，并已经安装yersinia。ping 114.114.114.114也不通，接着ifconfig发现 IP地址有的，然后手动配置了IP地址，发现还是Ping不通114.11.4.114.114，然后输入。更新源后，报错源无法解析，同时ping www.baidu.com也不通，那可能是DNS存在问题，更新一下DNS服务器。百度找了很久，有个回答比较接近，但一一尝试了几遍，还是无解，解决不了呀！•（2）Yersinia编译的时候，要选择gtk。

weilandeyongheng的专栏
4163
（53页PPT）新型智慧病房整体解决方案（附下载方式）

当前医疗场景存在三大核心矛盾：院内感染风险（如输液异常发现滞后）、信息孤岛现象（11类业务系统数据割裂）、管理效能不足（30%护理时间耗费在机械性工作）。实际案例显示，整体运营效率提升40%，患者满意度提高28个百分点，真正实现了"让技术有温度，让数据会说话"的价值理念。本文将从需求分析、技术架构、应用场景三个维度，深度剖析这份53页解决方案的创新价值与实践路径。床旁智能终端整合12项功能：包括体征自动采集（误差率<1%）、医嘱执行核对（100%条码校验）、智能床垫离床报警（响应时间3秒）等。

AI_data_cloud的博客
706
探索Llama 3.1：开源模型的本地部署与创新应用实践

在数字化转型的浪潮中，大型语言模型（LLM）以其卓越的处理能力和广泛的应用潜力，正在成为人工智能领域的新宠。 这些模型不仅在自然语言处理（NLP）领域取得了显著的进展，还在计算机视觉（CV）、多模态学习和科学计算等多个领域展现了巨大的应用潜力。 随着开源LLM的兴起，全球的Java开发工程师和研究者获得了一个宝贵的机会，可以在本地环境中部署和定制这些模型，以创造具有独特价值的应用程序。 2024年7月23日，Meta公司推出了Llama 3.1系列，这一举措为开源模型领域带来了新的活力。

忆~遂愿的博客
3561
SAP MM委外加工保姆级教程：从BOM配置到MIGO发货的完整避坑指南

本文提供SAP MM模块中委外加工的完整操作指南，涵盖从BOM配置到MIGO发货的全流程。详细解析委外采购和工序委外两种模式，包括主数据配置、采购订单创建及物料移动等关键步骤，帮助用户规避常见错误，提升供应链管理效率。特别适合制造业企业实施SAP外包业务参考。

weixin_26905487的博客
516
【colab】使用指南（复现代码）

白嫖colab复现代码

m0_55931547的博客
729
从零开始的BW(五) 外部系统供数之OData测试

5、激活添加的服务，如提示下图中的激活失败，根据生成URI在事务代码SICF目录中找到对应的服务，设置超时时间，设置完之后重新激活即可，详情可参考SAP note 1986626。如果刚才设置BY Odata的query在这没有显示，SE38执行程序EQ_RS_AUTOSETUP，选中需要生成服务的query，生成服务后再去添加服务。测试get方法，URI中默认的参数是?4、事务代码/IWFND/MAINT_SERVICE中添加服务，如果提示用户不再登陆，在事务代码前加上/O或者/N即可。

m0_61386064的博客
1100
S/4HANA Private Cloud 与 On-Premise 的 Key User Custom Fields 运输与升级避坑指南

本文探讨了SAP S/4HANA Cloud Private Edition和On-Premise系统中Key User Custom Fields的管理要点。文章指出，Custom Fields涉及元数据生成、对象一致性、传输治理等完整链路，操作不当会导致字段丢失或升级失败。关键建议包括：使用ATO Fiori App管理扩展项与传输绑定，配置正确的job user权限，避免在多系统并行开发同一字段。特别强调升级时需执行CFD_REGENERATE_IN_ONPREMISE报表，并通过标准传输机制推进变更

2007 年 ~ 2025 年，深耕 SAP 技术 18 年
185
colab写cuda

colab写cuda

weixin_43657921的博客
945
OKX 欧易 交易机器人开发基础

接口文档： https://www.okx.com/docs-v5/zh/#overview REST API 常用请求 查看账户余额 结果数据格式： 获取限价 结果格式： 获取指数行情 数据结构： 下单 结果数据： 获取未成交订单列表 返回结果： 撤单 结果结构：

Willin Wang 的全栈升级指南
2万+
DepthAI ML 训练项目教程

DepthAI ML 训练项目教程 1. 项目介绍 DepthAI ML 训练 是一个开源项目，旨在帮助用户训练自己的机器学习模型，并将其部署到 DepthAI 平台上。该项目提供了 Colab 笔记本，用户可以在 Google Colab 上运行这些笔记本，使用免费的 CPU/GPU 实例进行模型训练。训练完成后，用户可以将模型转换为与 DepthAI 平台兼容的格式，并部署到 OAK 相机上，...

gitblog_00030的博客
767
图解电动汽车：电动汽车的分类

前面《电动汽车简介》中简单介绍了电动汽车的分类，主要包括混合动力电动汽车（HEV）和纯电动汽车（BEV）两大类。其中，混合动力汽车又可分为非插电式混合动力汽车、插电式混合动力汽车（PHEV）以及增程式电动汽车（REEV）。 主要分类 简单来说，各类电动汽车的特点如下。 纯电动汽车（BEV）就是指动力来源完全由电能提供，由电动机驱动的汽车，并且电能储存在电池中。 混合动力汽车（HEV）则是指动力来源可以是化石燃料，也可以是电能，并且电能除了可以存储在电池中，还可以由化石能源转化而来。 非插电式混合动力汽车

程序员「阿基米东」的编程之旅
3080
OV9734 DATASHEET，完整规格书

OV9734完整规格书，包括电气参数，尺寸规格，寄存器配置表等

机器学习基础完整部署指南：Docker环境配置与Colab云端运行终极教程

想要快速入门机器学习但被复杂的数学理论吓退？🤔 本教程将为你提供ML-foundations项目的完整部署方案，让你在本地Docker环境或云端Colab中轻松运行所有机器学习基础教程。 ML-foundations是一个全面的机器学习基础课程项目，涵盖了线性代数、微积分、概率统计和计算机科学四大核心领域，为初学者构建坚实的理论基础。无论你是数据科学家、软件开发者还是AI爱好者，都能通过这个项

gitblog_01117的博客
421
计算机控制技术及应用

《计算机控制技术及应用》通过总结作者的科研成果和吸收国内外的先进理论、方法和技术，以计算机控制系统的网络化、开放化、智能化和集成化发展趋势为主线索，主要介绍计算机控制系统的基本概念和计算机控制系统的典型形式，计算机控制系统的数学描述与基本分析方法，以及数字PID控制器、最少拍控制系统、达林算法、状态变量设计法等设计方法及其各种改进算法。重点突出计算机控制系统输入输出通道接口的设计方法和典型控制系统的设计案例与实现方法等。

推荐深度学习利器：DepthAI ML Training

推荐深度学习利器：DepthAI ML Training 项目介绍 欢迎来到DepthAI ML Training项目的世界！这个开源库包含了一系列交互式的Colab笔记本教程，旨在手把手教你如何在云端高效地训练和优化自己的机器学习模型，然后将这些模型无缝部署到Luxonis的OAK相机上，实现边缘计算硬件上的实时加速。 项目技术分析 DepthAI是一个强大的平台，专为实现空间人工智能而设计。它...

gitblog_00070的博客
517
ET2012新版免狗免安装绿色软件

ET2012新版免狗免安祖昂绿色软件。，新界面，新视觉，
————————————————
版权声明：本文为CSDN博主「CaoChengtai」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/weixin_37589575/article/details/94591580
