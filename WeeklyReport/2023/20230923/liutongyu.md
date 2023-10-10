# 周报

## 做题情况

### A

    A没啥就骰子是3种拧法，每种都要两个面是有相同颜色的四个块组成的.
### B

    B就是并查集，找到最大的两个集合，再合并，最后求出x^2.icpc的网络赛第一场有比这个难一点的题，那个会了，这个也差不多。
### C

    C题是猜单词，统计每个单词中，未知的位置上的字母出现的次数（每个可能的单词上的未知位置上的字母只统计一次），然后只要有一个字母在每个单词的未知位置都出现过，那就输出“YES”。
    这里注意一下，如果未知位置上的字母是主持人给过的，那这个单词是不用统计的，肯定是错误答案。
### D

    D题反正最大数是1023，那也就总共10个位数，对每一个位数都模拟一下0和1，
    1.对于当前位只有1的情况，那就或上这个位数代表的值
    2.如果最后0的还是0，1是1，那就与上这个位数。
    3.如果最后0最后是1，1最后是0，那就先与再异或这个值。
    然后准从先与再抑或再或。三步解决
### E

    E是每隔两个就炸一次，这样每两个格只需炸三次。
    而隔三个总共要炸五次，没两个的便宜，所以用两个格一炸。
### F

    就求含a，b,a,的字符串的长度。
    先用pre[]记录b的前缀和。
    用i,j枚举含b字符串的起点和第二个a的起点。
    a1=i-pre[i];
    a2=n-j+1-(pre[n]-pre[j-1]);
    ans=max(ans,a1+a2+pre[j]-pre[i]);
### H
    没做。。。开的有点晚，关的有点早

### ICPC 2 D

    这题cwl一开始就要上网络流，虽然我不懂，但我大为震撼。
    后来听cwl说完题目大体意思，我觉得这不就只要看到所有的点就行，不是看所有的边。
    那就好办了，行列都取一遍最小的情况
    比较一下，就出来了，我直接口胡答案，cwl听从我的思路，交上，错了。。。
    额，忘了有人会倒贴钱了，倒贴的我全都要，主打的就是白嫖。
    将能白嫖的钱都白嫖了，然后再取最小，是负数，就加0.交上，又错了！！！
    正当我们百思不得其解的时候，我看到n是500，而负数能取-1e6,所以他暴int了
    改成ll就对了。。。

### ICPC 2 E

    大体意思是每个车的路线是按从起点到终点的最短路线来的，而且你只能从起点或终点上车，车也可以从终点回到起点（路线一致），你可以中途下车。
    一个人从1号城市出发，要看做几趟车可以到一个别的城市。
    难点在找最短路线与路线的遍历(因为路线都遍历最大也得n^2)

    cwl听完我的翻译讲解，提出了关键一问，有没有1,2,4,和1，3，4两个最短的路线，它应该怎么选？
    我确实没想到过。当然他也在自己读题目的时候找到了题目一开始就说了可以看作树。
    那么最短路线不就找到了,树上的两点最短的路线不就是LCA吗
    那怎么看需要几趟车呢？
    实际上我们一开始肯定是从1出发的，所以，我们先找以1为起始点的BUS路线，把终点入队，每次作类似
    LCA的操作时，也把没入过队的祖先入队，他们的步数为1。
    类似于广度优先
    然后每次取队头，出队。然后找以队头为起始点的路线，找他的另一个终点，然后同样在LCA的时候把他们的没入队 的祖先入队，他们的步数为当前队头的的步数+1；直到队列为空

    但是这样可能会超时，怎么再优化呢？
    实际上当我们找到一方的祖先pa是遍历过的时候，就不需要再找这一方的祖先了，
    因为他们的公共祖先一定会在1与刚刚找到的祖先pa的路径上的。
    所以可以说每个点几乎就遍历一遍。所以代码可行。
    我又一次口胡了解题思路，打代码的重任就交给cwl了。
    不得不说cwl的代码能力真的强，硬是当场把我这含糊不清的代码敲出来了

## 感想

    ·这周过的好快，我都还没开始复习高数。
    ·英语四六级终于报上了，用百词斩试试。
    ·下周看着有好多二课活动，希望多抢点。
    ps:github好慢，谁有什么灵丹妙药麻烦给我说说。
