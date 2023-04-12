### Info
* 英文队名 No Way,Hum?
* 中文队名 钱已到位
* 队员1 孙林壮
* 队员2 廖茂钧
* 队员3 刘茜童


### 比赛地址
http://acm.sdibt.edu.cn/vjudge/contest/view.action?cid=2104#overview


### 做出来的题目
A

#### A
* A题意
4个数，最大值加最小值减去其余两个值的差值，值为非负数。
* 思路
快排以后abs(a[3]+a[0]-a[1]-a[2])


### 补的题目
D F H

#### D
* D题意
求多边形最大面积。
* 思路
可推得规律当边长为凸函数时，面积最大。快排，奇数为从前到后，偶数为从后到前。（优先队列也可）

#### F
* F题意
n个电桩，每天k个命令，其中，1表示顺时针移动，-1表示逆时针移动，机器人最开始在第一个充电桩，问这个机器人一天里会经过充电桩s多少次
* 思路
跑循环，当到达s时，ans++，每回加n保证为非负数。

#### H
* K题意
住宾馆，每住k天可以获得一次免费住的机会，给你n天的价格，求最小花费。
* 思路
优先队列处理，队列长度为已有的可以免费的天数，每回push，然后pop最小值，最后剩余的则为应该免去的花费。

