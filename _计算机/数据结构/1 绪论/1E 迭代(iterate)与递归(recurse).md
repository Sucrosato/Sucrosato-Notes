*e.g. int SumI(int A[], int n)*
*考虑空间复杂度时不考虑输入*

## Decrease-and-conquer
将问题分解为：缩小的问题+平凡的问题

递归跟踪 recursion trace
    *e.g. int Sum(int A[], int n)
    *忽略调用递归实例*

递推方程
    e.g. 
        T(n)=T(n-1)+O(1)
        T(0)=O(1)

## Divide-and-conquer
e.g. 二分递归
    递推关系
        T(n)=2T(n/2)+O(1)
        T(0)=O(1)

## ~~Master Theorem~~
*用于评估分支问题的规模*
对于分治问题$T(n)=a\cdot T(n/b)+O(f(n))$
根据$f(n)$与$n^{\log_b{a}}$的复杂度关系，可得到总复杂度：
1. $f(n)=O(n^{\log_b{a}-\epsilon}),T(n)=\Theta(n^{\log_b{a}})$
2. $f(n)=\Theta(n^{\log_b{a}}\log^k{n}),T(n)=\Theta(n^{\log_b{a}}\log^{k+1}{n})$
3. $f(n)=\Omega(n^{\log_b{a}+\epsilon}),T(n)=\Theta(f(n))$
