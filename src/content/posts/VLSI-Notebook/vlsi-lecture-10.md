---
title: VLSI-Lecture-10
date: 2025-11-14
description:
tags:
  - 2025-autumn
  - VLSI
  - Notebook
image: "[[attachments/cover-11.png]]"
imageAlt: Concept Poster of PS Controller
imageOG: true
hideCoverImage: false
hideTOC: false
targetKeyword: vlsi multiplier data path
draft: false
---
# 二进制乘法器

## 乘法运算解构

### 无符号数乘法

$$
\begin{array}{ccccccccc}
 & & & 1 & 0 & 1 & 0 & 1 & 0 \\
\times & & & & & 1 & 0 & 1 & 1 \\
\hline
 & & & 1 & 0 & 1 & 0 & 1 & 0 \\
 & & 1 & 0 & 1 & 0 & 1 & 0 & \\
 & 0 & 0 & 0 & 0 & 0 & 0 & & \\
+ 1 & 0 & 1 & 0 & 1 & 0 & & & & \\
\hline
1 & 1 & 1 & 0 & 0 & 1 & 1 & 1 & 0 & \\
\end{array}
$$

$$
M \text{位} (X=\sum_{i=0}^{M-1} X_i 2^{i}) \times N \text{位} (Y=\sum_{j=0}^{N-1} Y_j 2^{j})
$$
结果（将 Z 展开为 X 和 Y 的乘积形式）：

$$ 
Z=X \times Y=\sum_{k=0}^{M+N-1} Z_k 2^{k} = \left(\sum_{i=0}^{M-1} X_i 2^{i}\right)\left(\sum_{j=0}^{N-1} Y_j 2^{j}\right)
$$
$$
=\sum_{i=0}^{M-1}\left(\sum_{j=0}^{N-1} X_i Y_j 2^{i+j}\right) =\sum_{i=0}^{M-1}\sum_{j=0}^{N-1}(X_{i}Y_{j})\cdot 2^{i+j}
$$
我们可以构建一个M行N列的**位积矩阵**（这个$M$行$N$列的矩阵中的每一个元素$X_iY_j$都代表一次**AND**操作）：

$$ 
\text{位积矩阵}=\begin{bmatrix}
X_{M-1}Y_{N-1}&X_{M-1}Y_{N-2}&\cdots &X_{M-1}Y_{0}\\
X_{M-2}Y_{N-1}&X_{M-2}Y_{N-2}&\cdots &X_{M-2}Y_{0}\\
\vdots&\vdots&\ddots&\vdots\\
X_{0}Y_{N-1}&X_{0}Y_{N-2}&\cdots &X_{0}Y_{0}
\end{bmatrix} 
$$

最终乘积$Z$是这个矩阵中所有元素乘以其对应的二进制权重后的总和。矩阵中位于第$i$行、第$j$列的元素$X_{i}Y_{j}$的权重是$2^{i+j}$。

### 有符号数乘法

由于符号位有负的权重，所以 X 和Y 可以解构为：

$$ 
X=-x_{m-1}2^{m-1}+\sum_{i=0}^{m-2} x_{i}2^{i} 
$$ $$ 
Y=-y_{n-1}2^{n-1}+\sum_{i=0}^{n-2} y_{i}2^{i} 
$$
由此，乘积结果可表示为：

$$ 
XY = x_{m-1}y_{n-1}2^{m+n-2} + \sum_{i=0}^{i=n-2}\sum_{j=0}^{j=m-2} x_jy_i 2^{m+n-4} - \left(x_{m-1}\sum_{i=0}^{n-2}y_i 2^{m+i-1} + y_{n-1}\sum_{i=0}^{m-2}x_i 2^{n+i-1}\right) 
$$

难点在于出现了**减法**。在数字集成电路设计中，我们希望只使用加法器阵列。因此，必须利用==补码==的性质将“减法”转换为“加法”。

$$
\begin{array}{ccccccccc}
 & & & & x_3 & x_2 & x_1 & x_0 & & \\
 & & & & y_3 & y_2 & y_1 & y_0 & \\
\hline
 & & & & & x_2y_0 & x_1y_0 & x_0y_0 & & \\
 & & & & x_2y_1 & x_1y_1 & x_0y_1 & & & \\
 & & & x_2y_2 & x_1y_2 & x_0y_2 & & & & \\
 & x_3y_3 & & & & & & 1 \\
 & 1 & \overline{x_2y_3} & \overline{x_1y_3} & \overline{x_0y_3} & 1 & 1 & 1& \\
 & 1 & \overline{x_3y_2} & \overline{x_3y_1} & \overline{x_3y_0} & 1 & 1 & 1& \\
+ & & & & & & & 1 \\
\hline
 & S_6 & S_5 & S_4 & S_3 & S_2 & S_1 & S_0 \\
\end{array}
$$

# 部分积的产生

![](attachments/部分积产生电路.png)
*部分积产生电路*

这里的与门使用的是 NAND ，由于加法器的反相特性，虽然NAND门的输出是AND门输出的**反码**，但后续的电路（如加法器）通常可以设计为接受反相输入，或者利用加法器本身的逻辑特性来==抵消这个反相==。

## 部分积压缩 -- Booth 编码

如果乘数中某一位是0，该行部分积全为0，对结果无贡献。但我们无法控制输入数据中0的数量。

**编码目标**：通过对乘数进行编码，将连续的“1”序列转换为==更稀疏的形式==，从而减少实际需要运算的非零项数目。


# 部分积的累加

# 最终相加

# 高性能乘法器架构