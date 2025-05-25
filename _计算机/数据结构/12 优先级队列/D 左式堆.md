节点分布偏向于左侧；
合并操作只涉及右侧
## NPL *Null Path Length*
引入外部节点null，转为真二叉树
npl(NULL) = 0
npl(x) = 1 + *min*(npl(lc(x)), npl(rc(x)))
极大满子树的高度：npl(x)

## 左倾
对任何节点x，`npl(lc(x)) >= npl(rc(x))`
\*左子堆不一定大于右子堆
#### 右侧链
一路向右，外部节点（极大满子树）的高度为npl(x)<=logn
## （合并算法）实现 *by Crane*
不是完全二叉树，不适合用向量
`class PQ_LeftHeap : public PQ<T>, public BinTree<T> {`

\*合并前需要先保证a的根大于b
将右子树递归地与B合并，
并且比较其与左子树的NPL视情况交换

O(logn)
## 插入与删除
借助合并完成
