多任务调度 %%门诊医生%%
call-by-**priority**
#### 功能接口：
```c++
virtual void insert(T) = 0; //纯虚函数，必须给出实现
virtual T getMax() = 0;
virtual T delMax() = 0;
```
## 基本实现
#### 向量
无论如何都不可行
#### 有序向量
维护（插入）成本过高
列表类似
#### BBST
O(logn)
高级数据结构->简单数据结构
只需要维护 *偏序* 关系，而不需要 *全序*
