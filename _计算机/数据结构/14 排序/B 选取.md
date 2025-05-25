## 选取众数 *majority*
`excel: large(range, rank); median(range);`
\*这里的众数：超过一半的数（可能没有众数）
- 众数一定是中位数
#### 减而治之
`template <typename T> T majEleCandidate`
m在某个前缀恰好占一半 + m在后缀中也是众数 -> m是众数
每次剪除maj正好占一半的前缀，考察后缀
不变性：A的众数永远是后缀的众数，否则没有众数
## 通用算法
取第k个元素
- 排序：
- 小顶堆：k越小越快
- 大顶堆插入删除
- 大小顶堆
#### quickSelect()
利用`partition()`
最坏情况仍然不行
#### `linearSelect()`
选Q
划分成n/Q块
各自排序，取中位数
找到中位数的中位数
分成L-E-G,只保留三者之一
递归

单次复杂度O(n)，问题规模至多只剩75%（可视化）

取足够小的Q，使最终递推复杂度为线性


