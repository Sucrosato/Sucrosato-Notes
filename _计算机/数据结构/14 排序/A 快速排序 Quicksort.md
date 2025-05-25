![[Pasted image 20250420143807.png]]
## 算法
#### 分治
递归分成两个子序列、$max(S_L) \leq min(S_R)$
#### 轴点
左侧不大于，右侧不小于
```c++
::quickSort(Rank lo, Rank hi){
partition(
quickSort(
quickSort(
}
```
- 不一定存在
    乱排序列 *derangement*
- 通过 *交换* 将所有点转换成轴点
#### 轴点的构造
选取首元素为轴点候选->
分成L,U,G->
将U中划分到L和G（左右轮流利用空闲空间拓展）->
分出轴点，继续递归<-
## 性能
- 不稳定
    相等元素可能颠倒
- 就地
- 最好：O(nlogn)
- 最坏：O(n^2)
- 平均：O(nlogn)，$\approx 1.39n \ln n$
## 快速划分（LGU）版
