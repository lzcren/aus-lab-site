# MCTS + level-K 博弈决策

## 概述
蒙特卡洛树搜索（MCTS）结合 Level-K 认知层级模型，用于多智能体博弈、飞行器冲突规避、自主决策。
Level-K 用来建模对手认知层次，MCTS 做前向搜索评估动作收益。

## 理论要点
- UCT：上置信区间，平衡探索与利用
- Level-K：k=0（随机）、k=1（对手k=0）、k=2（对手k=1）……
- 融合思路：用Level-K对手模型作为MCTS环境，模拟对手行为

## 公式
$$
UCB(s,a) = Q(s,a)+C\sqrt{\frac{\ln N(s)}{N(s,a)}}
$$
$Q(s,a)$：动作价值；$N(s)$：访问次数；$C$：探索系数

## 代码示例
```python
# 预留 MCTS UCT 简易框架