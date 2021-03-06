# 贝叶斯网络

**贝叶斯网络（Bayesian Network）**，又称**有向图模型（Directed Graphical Model）**或**信念网络（Belief Network）**。


## 定义

有向非循环图 $G$ 中，每个节点对应 $K$ 维随机向量 $X$ 中的一个变量，有向边 $e_{ij}$ 表示随机变量 $X_i$ 和 $X_j$ 之间具有因果关系。

令 $X_{\pi_k}$ 为变量 $X_k$ 的所有父节点变量集合，$P(X_k \mid X_{\pi_k})$ 表示每个随机变量的**局部条件概率分布（Local Conditional Probability Distribution）**。

如果 $X$ 的联合概率分布可以分解为每个随机变量 $X_k$ 的局部条件概率的连乘形式，即：

$$
p(x) = \prod_{k=1}^K p(x_k \mid x_{\pi_k})
$$

那么称 $(G,X)$ 构成了一个贝叶斯网络。


### 条件独立性

如果两个节点被一条有向边直接连接，那么它们一定非条件独立，且之间具有因果关系，父节点是『因』，子节点是『果』。


### 局部马尔可夫性质

每个随机变量在给定父节点的情况下，条件独立于它的非后代节点：

$$
\newcommand{\indep}{\perp \!\!\! \perp}

X_k \indep Z \mid X_{\pi_k}
$$

其中 $Z$ 为 $X_k$ 的非后代节点。
