## 好后缀
按BM_BC算法，如果匹配部分成功，则可吸取 *经验*
获得好后缀，从P中选择最靠后的相同子串，前移
`gs[]`，发生不匹配时前移的量
## 构造gs表
`MS[j]`：`P[0, j]`的所有后缀中与P的某一后缀匹配的最长者
->`ss[j]`：长度 max{0 <= s <= j+1 | `P(j - s, j] = P[m - s, m)`}
->`gs[j]`：
![[Pasted image 20250419210953.png]]
~~？？~~
O(m^2)，可优化至O(m)
## 性能
预处理：$O(|\Sigma|+m)$
查找：
    最好 O(n/m)
    最差 O(n+m)
## 各算法性能
![[Pasted image 20250419211405.png]]


