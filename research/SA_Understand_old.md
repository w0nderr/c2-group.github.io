
# 态势认知——理解

## 概述

随着网络入侵行为趋于规模化、复杂化、间接化，国家间信息对抗形势逐渐严峻，对网络安全技术提出了更高的要求。与对已产生的攻击行为进行取证和控制相比，态势认知和意图推断技术能够主动地收集动态的网络态势信息，分析并准确预测帮助管理员做出准确防御和应急性决策，具有重要的意义。意图推断与意图识别意义相近，最早来源于人工智能领域中的计划识别(Plan Recognition)。计划识别是人工智能领域中被广泛研究的内容，最早的研究是基于规则的推断系统。计划识别被用于进行agent行为意图的识别，是通过对agent的行为进行观察来推断agent的目的，可以分成两大类：keyhole recognition和intended recognition，前者agent不知道自身的行为在被观测，后者中agent会执行有利于其计划被识别的行为。在网络安全领域，意图推断可以帮助管理者对可能发生的网络攻击进行及时的感知，并采取措施进行应对，常用于风险评估中。常见的意图推断模型有攻击树、攻击图、贝叶斯网络等。

攻击树模型最早是基于故障树模型的概念提出的。攻击树中的叶子节点表示攻击方法，根节点表示了攻击者的目标。攻击树中的节点分为AND节点和OR节点，其中AND节点表示只有所有孩子节点都实现，父节点才能实现，OR节点表示任意一个孩子节点实现了，父节点就可以实现。但是，攻击树在刻画攻击者的攻击路径时确定性较强，当攻击者在某次攻击中改变攻击手段时，攻击树往往会失去作用。

攻击图与攻击树相似，以有向图的方式来表答攻击者利用存在的脆弱性对网络或信息系统进行攻击的所有可能的攻击路径，全面的反映了网络或信息系统中脆弱点利用之间的依赖关系。攻击图自身不能对不确定性进行表示，因此结合贝叶斯网络形成贝叶斯攻击图是研究的热点，例如杨宏宇等提出了一种基于攻击图的多Agent网络安全风险评估模型，利用多个agent进行信息搜集来对攻击者的意图进行推断；高妮等提出了一种基于贝叶斯攻击图的动态安全风险评估模型，考虑了攻击图节点的资源属性，根据攻击者的实际攻击对后验风险进行推断；陈小军等在攻击图模型中引入了转移概率表，用其刻画单步攻击检测结果的不确定性，使推断结果更加符合实际。

贝叶斯网络是进行推断的重要工具。贝叶斯网络是一种用于描述变量间不确定性因果关系的图形网络模型，由节点、有向连线和条件概率表组成，其中有向连线代表节点间的因果依赖关系。贝叶斯网络的构建可由专家完成，在具有足够数据的情况下可以通过结构学习算法获取。常见结构学习算法分为三类：基于约束的算法，基于评分搜索的算法和混合算法。除了三类主流算法之外，还有动态规划结构学习、模型平均结构学习和不完备数据集的结构学习等算法。

现有的推断算法来源可以大致分为两种，一种从攻击图或是攻击树等常规图模型而来，利用现有的结构和定义的概率进行风险的计算，并根据攻击者的攻击行动是否被检测来对攻击者采用某一攻击路径的后验概率进行推断；另一种是贝叶斯网络而来，将贝叶斯网络中的推断算法应用到现实的问题中去。基于贝叶斯网络的推断算法是目前推断算法的主流，贝叶斯网络。贝叶斯推断算法主要可以分为两大类：精确推理算法和近似推理算法，前者主要用于网络规模较小、节点较少、关系不是很复杂的网络上。


## 研究选题

## 1、内网用户行为分析与画像 ##

![](./project/幻灯片15.jpg)
![](./project/幻灯片16.jpg)
![](./project/幻灯片17.jpg)

## 2、面向攻击意图推断的贝叶斯网络学习方法 ##

![](./project/幻灯片18.jpg)
![](./project/幻灯片19.jpg)
![](./project/幻灯片20.jpg)

## 3、异常检测及推断模型鲁棒性研究 ##

![](./project/幻灯片21.jpg)
![](./project/幻灯片22.jpg)
![](./project/幻灯片23.jpg)

## 4、研究资源 ##

- 在实际应用中，单纯依赖机器学习模型进行检测而忽视威胁情报会为攻击者的攻击埋下隐患。网络威胁情报（Cyber threat intelligence，CTI）是对传统网络安全的重要补充，对于研究人员来说，其可利用的威胁情报主要从开源网站上进行获取，这类威胁情报可以粗略划分为四种：IP地址信息、域名信息、漏洞数据库和开源情报信息库（例如有关安全的博客和论坛等）。在攻击检测过程中，可以直接自动化利用的是恶意IP地址库和恶意域名库，分属于粗分类的前两种。

- 恶意IP地址库是研究人员最容易获得的威胁情报之一，这些威胁情报被用于浏览器的访问黑名单中，当客户端发出的请求中包含这些地址时，浏览器便会进行阻拦。有很多公开网站发布恶意IP列表，其中，FireHOL 维护的恶意IP库是一个非常好的选择。FireHOL本身是Costa Tsaousis开发的用来对Linux内核防火墙的netfilter中IP表进行定制的一种shell脚本，其开发者提供了一个良好的恶意IP地址库，主要由四个来源的IP地址构成：fullbogons，出现在这些IP地址列表中的IP通常是DDOS攻击的来源，因此在一个路由器的路由表中这些地址不应该被添加进去；spamhaus drop and edrop，这个列表中包含了被专业的网络犯罪行动和钓鱼邮件使用后遗留下的IP；dshield，该IP地址包含了近三天排名前20的C类IP地址的攻击源IP；malware lists，顾名思义，是那些恶意软件或木马的常用网址。该综合IP地址库上的IP源地址会实时更新，并可以进行下载来对内部的应用IP地址库进行补充。

- 恶意域名库主要用于对僵尸网络、钓鱼页面和恶意软件进行防范。当一个用户访问的页面地址被包含在恶意域名列表中时，为用户安全考虑会对用户告警。很多网站都维护有向大众公开的相应的恶意域名库，在研究中可以从这些公开网站上获取相应数据。例如，PhishTank 是一个包含了众多钓鱼网址的网站，其由企业家David Ulevitch于2006年10月创办，是其主公司OpenDNS的一个分支，其主公司会利用自己开发的一套系统对用户请求检测的网站进行检测，并根据用户的投票来判断此网站是否为钓鱼网站，PhishTank上的大量记录由此而来。除此之外，还有DNS-BH project 、Malware Domain List等网站也提供了大量恶意域名信息。

- 常用的网络节点重要性排序指标有：度值、介数、接近中心性、k-壳值和特征向量等。其中，度值排序是一种局部排序方法，即网络中一个节点的度值越大则该节点越重要；介数是以经过某个节点的最短路径数量来评估节点重要性的方法，即经过某节点的最短路径数越多，该节点重要性越大；节点的接近中心性为节点与网络中其他节点距离平均值的倒数，即节点接近中心性越大则该节点越重要；k-壳分解是一种对网络中节点重要性粗粒化划分的方法；特征向量的基本思想为：网络中节点的重要性既与节点的度值大小有关，同时也与邻居节点的重要性有关。
- [https://en.wikipedia.org/wiki/Credal_network](https://en.wikipedia.org/wiki/Credal_network)
- Cozman F G. Credal networks[J]. Artificial Intelligence, 2000, 120(2):199-233.
- Vergari A, Mauro N D, Esposito F. Simplifying, Regularizing and Strengthening Sum-Product Network Structure Learning[C]// Joint European Conference on Machine Learning & Knowledge Discovery in Databases. 2015.

- 由于目前已有大量的贝叶斯网络学习研究，以及相关数据和构建好的实际应用模型，我们将利用这些公开的数据进行学习，并与实际模型相比较，从而对本项目的算法以及公开发表算法进行评价。比较有名的公开数据集包括：牛津大学的BN Learn（[http://www.bnlearn.com/](http://www.bnlearn.com/)），澳大利亚人工智能协会的ABNMS数据集（[http://abnms.org/bnrepo/](http://abnms.org/bnrepo/)），以色列希伯来大学的BN Repository（[http://www.cs.huji.ac.il/Repository/](http://www.cs.huji.ac.il/Repository/)），NORSYS软件公司的Net library数据集（[http://www.norsys.com/netlibrary/](http://- www.norsys.com/netlibrary/)），以及HUGIN公司的BN Forum数据集（[http://forum.hugin.com/](http://forum.hugin.com/)）等。

- 可以基于这些通用数据集中的贝叶斯网络模型，进行编程实验，并将软件工具包BNT（Bayes Net Toolbox for Matlab）集成到开发环境中，通过从真实模型中采样得到训练用目标数据集，通过引入一定的噪声采样产生源数据集，以便于进行多任务和迁移学习，实试验算法均在不同样本数据集上独立运行 100次进行测试。 在得到学习结果后，对不同学习算法进行评价，包括计算实验得到的网络与真实网络的结构编辑距离（将算法确定的最优图结构转化为标准的网络结构所需要的平均运算总数目），以及参数的K-L散度（Kullback–Leibler Divergence，用于计算概率分布之间的距离）等。


