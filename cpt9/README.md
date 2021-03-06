# 动态规划

## 基础概念

斐波那锲数列: fn(n) = fn(n-1) + fn(n-2)

将原问题拆解为若干子问题，同时保持子问题的答案，是每个子问题只就一次，最终获得答案

避免出现重叠子问题
- 记忆化搜索  自顶向下
- 动态规划 自底向上

70 [爬楼梯](https://leetcode-cn.com/problems/climbing-stairs/)

120 [三角形最小路径和](https://leetcode-cn.com/problems/triangle/)

64 [最小路径和](https://leetcode-cn.com/problems/minimum-path-sum/)

---

## 发现重叠子问题

### 例题

343 [整数拆分](https://leetcode-cn.com/problems/integer-break/)

### 习题

279 [完全平方数](https://leetcode-cn.com/problems/perfect-squares/)

**91** [解码方法](https://leetcode-cn.com/problems/decode-ways/) 斐波那锲模型

62 [不同路径](https://leetcode-cn.com/problems/unique-paths/)

63 [不同路径 II](https://leetcode-cn.com/problems/unique-paths-ii/)

---

## 状态的定义和状态的转义

### 例题

198 [打家劫舍](https://leetcode-cn.com/problems/house-robber/)

状态的定义：考虑偷取`[x..n-1]`范围内的房子 函数定义

根据对状态的定义，决定状态的转移 

状态转换方程`f(0)=max{v(0)+f(2), v(1)+f(3), v(2)+f(4), ... , v(n-3)+f(n-1), v(n-2), v(n-1)}`

### 习题

213 [打家劫舍 II](https://leetcode-cn.com/problems/house-robber-ii/)

**214** [打家劫舍 III](https://leetcode-cn.com/problems/house-robber-iii/)

**309** [最佳买卖股票时机含冷冻期](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-with-cooldown/)

---

## 0-1背包问题

### 基础概念

有一个背包，容量为C（Capacity）。现在有n种不同的物品，编号为0..n-1，其中每件物品的重量为w(i)，价值为v(i)。

问可以向这个背包中盛放那些物品，使得在不超过背包容量的基础上，物品的总价值最大

F(n, C) 考虑将n个物品放到容量为C的背包中，使得其价值最大

状态转移方程：F(i, c) = F(i-1, c) = v(i) + F(i-1, c - w(i)) 求后面两者的最大值

### 例题

416 [分割等和子集](https://leetcode-cn.com/problems/partition-equal-subset-sum/)

典型的背包问题，在n个物品中选定一定的物品，填满sum/2的背包

F(n, C) 考虑将n个物品填满容量为C的背包

F(i, c) = F(i-1, c) || F(i-1, c-w(i))

### 习题

322 [零钱兑换](https://leetcode-cn.com/problems/coin-change/)

322 377 474 139 494
