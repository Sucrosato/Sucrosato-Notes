问题：Minimum(Minimal) Spanning Tree
找到一颗子树 *spanning tree* 覆盖所有的点，带权边的和最少
优点：
    可有效计算
    众多优化问题的基本模型
    NP问题的好近似解(Euclician
允许权值为负数
等边：可利用组合数消除歧义

## Prim算法
引入了 *cut* ：将所有点一分为二，*cross edge*
Prim认为：任何一个cut的最短桥一定会被MST采用
漏洞：可能一边是同一个点；可能采用多条边；一个最短边只能说属于 *某一* MST

任选一个点，与其他点形成cut，选最短边，并将连通的点加入



优先级：到当前树的距离
区别：不用加“邀请人”的权重