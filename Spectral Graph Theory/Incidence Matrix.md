## 关联矩阵（Incidence Matrix）

#### 关联矩阵

​		**定义：给定节点数为 $m$，边数为 $n$ 的图 $G$，其关联矩阵 $\nabla=\nabla_G$ 是一个 $m\times n$ 矩阵，它的定义如下：**
$$
{[\nabla_G]}_{v,e} = \begin{cases}
   1 &\text{if edge } e \text{ starts from node } v \\
   -1 &\text{if edge } e \text{ ends at node } v \\
   0 &\text{otherwise } 
\end{cases}
$$
​		**定理^[2\ p4]^：$L=\nabla\nabla^T$**

​		**证：**$[\nabla\nabla^T]_{ij}=\sum_{e\in E(G)} \left([\nabla]_{v_i,e} \right) \left([\nabla]_{v_j,e} \right)$，分三种情况讨论：

- 当 $i=j$
    $$
    [\nabla\nabla^T]_{ij}=\sum_{e \in E(G)} \left([\nabla]_{v_i,e} \right)^2=\sum_{e\ incident\ to\ v_i} 1=deg(i)
    $$

- 当 $i\neq j$ 且 $v_i$ 与 $v_j$ 之间不存在边
    $$
    [\nabla\nabla^T]_{ij}=\sum_{e\in E(G)} \left([\nabla]_{v_i,e} \right) \left([\nabla]_{v_j,e} \right)=0
    $$
    因为对于每一个 $e\in E(G)$，$[\nabla]_{v_i,e}  $ 与 $[\nabla]_{v_j,e} $ 其中至少有一个为 $0$

- 当 $i\neq j$ 且 $v_i$ 与 $v_j$ 之间存在边 $e'$
    $$
    [\nabla\nabla^T]_{ij}=\sum_{e\in E(G)} \left([\nabla]_{v_i,e} \right) \left([\nabla]_{v_j,e} \right)
    =\left([\nabla]_{v_i,e'} \right) \left([\nabla]_{v_j,e'} \right) = -1
    $$

上面不就是拉普拉斯矩阵的定义吗！

​		**推论：$L_G$ 是半正定矩阵** 
$$
x^TL_Gx=x^T\nabla\nabla^Tx = (\nabla^Tx)^T(\nabla^Tx)=\|\nabla^Tx\|_2^2\geqslant0
$$
这是证明 $L_G$ 是半正定矩阵的第二种证法。

#### 参考文献

- [1] [Laplacian matrix - Wikipedia#Symmetric_Laplacian_via_the_incidence_matrix](https://en.wikipedia.org/wiki/Laplacian_matrix#Symmetric_Laplacian_via_the_incidence_matrix)
- [2] [Topics in Theoretical Computer Science: An Algorithmist's Toolkit: Properties of the Laplacian, positive semidefinite matricies, spectra of common graphs, connection to the continuous Laplacian - MIT OpenCourseWare](https://ocw.mit.edu/courses/mathematics/18-409-topics-in-theoretical-computer-science-an-algorithmists-toolkit-fall-2009/lecture-notes/MIT18_409F09_scribe2.pdf)

