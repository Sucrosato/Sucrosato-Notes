Vector的形、Tree的神
#### 完全二叉树
平衡因子非负：
    0，则左子树为满树
    1，则右子树缺失了连续的一段
#### 完全二叉堆
用向量实现的完全二叉树
```c++
#define Parent(i) (i-1) >> 1
#define LChild(i) i << 1 + 1
#define RChild(i) i << 1 + 2
```
继承：
`template <typename T> ComplHeap : public PQ<T>, public Vector<T>`
#### 堆序性
- 任何孩子的值不大于其父亲
`::getMax(){return _elem[0]}`

## 插入与上滤
只需插入到向量末尾
- 如果发生了堆序性的破坏：
    与父亲交换；
    如果恢复了堆序性，则插入结束；
    否则，重复和新的父亲互换位置
#### 实现
`::insert()`
`::percolateUp(Rank i)`
`::parentValid()`
备份待提升节点，可达到`O(logn+2)`
## 删除与下滤
将末尾元素代替被删除元素
每次挑两个孩子中**大的一个**进行交换，直到修复逆序缺陷
#### 实现
宏！
常数：多叉堆中很重要
## 批量建堆 *Heapification*
 `::PQ_ComplHeap(T* A, Rank n)`
自上而下的上滤：蛮力，深度求和，O(nlogn)
自下而上的下滤：高度求和，O(n)
