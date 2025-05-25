w-sorting -> w-ordered ->
...->
1-sorting
步长序列 step sequence：各矩阵宽度的逆序列
又名：*递减增量法 diminishing increment* 

多维向量的一维表示 vec\[i, k]->vec\[i+kw]
内部排序采用 *输入敏感* 的初等排序：插入排序

#### Shell序列
H<sub>shell</sub>={1, 2, 4, 8, ..., 2<sup>k</sup>}
问题：奇偶独立，直到1-sorting之前都有O(n^2)逆序对没有消除

#### 邮资问题
Linear Combination
N(g, h) 不能用g和h线性表示
数论：
    x(g, h) = max{N(g, h)} = (g - 1)\*(h - 1) - 1
Knuth：
    g-ordered by h-sorting -> h-ordered && g-ordered ->
(g, h)-ordered ->
(mg + nh)-ordered

则逆序对只出现在x(g, h)以内的区域：适用于输入敏感

更多的希尔序列


