title: yo GA
speaker: 丁丁
url: https://github.com/coolguy001tv/nodePPT/share/ga
transition: zoomin
theme: dark
date: 2017/05/05





[slide]
# yo, GA


[slide]
# yeoman
----
THE WEB'S SCAFFOLDING TOOL FOR MODERN WEBAPPS

[slide]
# Tools
----
* yo
* grunt/gulp
* npm

[slide]
# GA
## Genetic Algorithm
---
遗传算法（Genetic Algorithm）是模拟达尔文生物进化论的自然选择和遗传学机理的生物进化过程的计算模型，是一种通过模拟自然进化过程搜索最优解的方法  {:&.zoomIn}



[note]
* 这是一个看起来高深莫测，但是其实很简单的算法
* 人工智能 机器算法 2016人工智能元年
* 先了解一些基本概念，然后听我讲个故事
[/note]

[slide]
# 重要概念
-----
* 种群(Population)与个体
* 染色体(Chromosome)
* 基因(Gene)
* 生存竞争，适者生存
    * 适应度函数
* 遗传与变异
    * 交配(Mate)/交叉(Crossover)
    * 变异(Mutate)

[slide]
# 关于遗传算法的故事
----
* 袋鼠的故事  {:&.zoomIn}
* 扇贝与Firefox的故事
* 机器人Bob画梦中情人


[slide]
![图片](/flow.png)



[slide]
# 0-1背包问题的遗传算法实现
------
有一个背包，最多承重为C=150的物品，现在有7个物品，编号为1~7，重量分别是w=[35,30,60,50,40,10,25]，价值分别是p=[10,40,30,50,35,40,30]，现在从这7个物品中选择一个或多个装入背包，要求在物品总重量不超过C的前提下，所装入的物品总价值最高。

[note]
问题可以描述为：给定一组物品，每种物品都有自己的重量和价格，在限定的总重量内，我们如何选择，才能使得物品的总价格最高
直接看代码
[/note]


[slide]
# 优化与注意事项
-----
* 精英主义(Elitist Strategy)选择 {:&.zoomIn}
* 轮盘赌算法( Roulette Wheel Selection )
* 重复的基因
* 超重种群
* 结束条件
* 参数调整
* 不一定能拿到最优解（变异的重要性）


[slide]
# 还有哪些问题可以用遗传算法解决
-----
* 求解函数 f(x) = x + 10*sin(5*x) + 7*cos(4*x) 在区间[0,9]的最大值  {:&.zoomIn}
* TSP(Travelling Salesman Problem)问题


[note]
参考资料中有详细解答
[/note]

[slide]
# 其他最优解算法
-----
* 贪心算法  {:&.zoomIn}
* 蚁群算法
* 模拟退火算法


[note]
神经网络
[/note]


[slide]
# 参考资料
-----
* [百度百科](http://baike.baidu.com/link?url=A3AiO7aWvh5tNzI78zySqIYwJP97rG8LyWb5xZrYcdEOx6gZjTyuf3qbyhuvB3bapLYMgZJmjV1XIWocknQzKMaUP_lZuDI90cSit9HAGkvyCYwW8md93zC9gXJC8Az4)
* [机器学习之Javascript篇：遗传算法介绍](http://www.cnblogs.com/wangweiqiang/p/5039525.html)
* [扇贝与Firefox的故事，机器人Bob画梦中情人，求解函数最大值](https://www.zhihu.com/question/23293449)
* [机器学习之Javascript篇：遗传算法介绍](http://www.cnblogs.com/wangweiqiang/p/5039525.html)
* [遗传算法入门](http://www.cnblogs.com/heaad/archive/2010/12/23/1914725.html)
* [遗传算法解背包问题](https://segmentfault.com/a/1190000004989612)

http://alteredqualia.com/visualization/evolve/