%%最经典的平衡二叉树%%
$BST \subset BBST \subset CBT(难以达到)$
重平衡：BST->BBST，O(logn)

平衡因子：$$balFac(v)=height(lc(v))-height(rc(v))$$
平衡标准：$$\forall v,|balFac(v)|\leq1$$
则可称为AVL树

- 适度平衡
- 至少包含 $S(h)=fib(h+3)-1\to\Phi^h$节点

## 接口
3个#define
BinNodePosi\<T\> insert
bool remove

插入一个节点导致若干个祖先 *失衡*
删除一个节点最多导致 *一个* 节点失衡（不引起失衡的祖先高度变化）

## 插入
#### 单旋
-：zag(g)，g是最深（最低）的失衡祖先，其上祖先一同复衡
O(1)
特点（限制）：方向相同，zag-zag / zig-zig
#### 双旋
右左：zigzag
#### 实现
插入
检查
*第一个失衡的至少是祖父*

## 删除
#### 单旋
方向相同
可能导致祖先继续失衡，O(logn)
#### 双旋
之字形
#### 实现
*第一个失衡的可能是父亲*
## （3+4）-重构
`connect34(BinNodePos ...)`
通过对左孩子/右孩子的判断，用`connect34()`直观地实现单旋/双旋

## 综合评价
- 优点
O(logn)、空间O(n)
- 缺点
借助高度/平衡因子进行额外封装
实测复杂度与理论有差距
拓扑结构变化量可高达$\Omega(\log n)$
