
# 纵深防御与网络阻断

## 背景
假如单点被突破，如何在网络内进行阻断？如何组织2线、3线防御？
黑客进来后，网络环境其实非常复杂，他在其中也是一个寻找、摸索的过程。例如，IDC/OA  外部攻击进来后，可能通过web 近来，也可能过钓鱼进OA，再进去IDC。
如何从攻击链的角度来卡位：入口、出口、系统组件间联系、边界的关联点，尽可能从黑客视角，找到出入口。目前人工鉴别服务及网络上的关键点。
对外服务，要绑定本地端口，所以端口关键，所以从端口入手，还没有到达智能去感知
蜜罐议案如何部署？理想条件下，IDC主机同时也是蜜罐，危害可控的情况下，尽可能多的搜集信息，判断意图


## 问题
	*
如何权衡控制手段的风险、效果、成本
	*
如何结合攻击链条，选取关键点，建立纵深防御？
	*
如何找出接入通道上的关键点？比如，能否找出需要重点防御的点？



构想的问题
	*
恶意软件的扩散阻断
	*
动态隔离策略
	*
意图的诱导



可能的场景：
	*
漏洞的修复，但可能不需要那么复杂的模型，如考虑漏洞修复的时效性选择，成本高、低，有些立刻停止服务；
	*
内网中有中心机，有些通过授信，有些通过破解密码，不同过程有不同的成本，服务器之间穿梭的路径，成本不同。



## 解决思路
如果形成了对风险的评估，如果有人想利用，则可以基于其渗透的链条，及其在拓扑中体现出来的特征，在各点上进行卡位，插入探头、进行阻断等。

难点
防控成本：自身（防控）系统可用性、给原来系统增加的延时、策略的准确性；服务质量、准确度
轻量可控：针对某个进程的
决策算法是否在线？开销？
网络规模对算法速度的影响？
传播模型，如何定权值？攻击、时间？
拓扑、漏洞、知识库全部建立以后，才会到达这个阶段，需要建立在知识图谱基础上，对动作的效果有先验知识。资产识别、知识图谱，然后才能是决策
成本难以量化
现在的决策比较宏观，通过业务、系统两层去看，控制目前考虑主机的进程、调用的控制，网络对数据的删除
