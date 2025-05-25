问题：带权图 最短路径
string computer

#### 拉绳子：
每次选最短的，然后由他给他下面的邻居更新优先级
```c++
template <typename Tv, typename Te> struct DijkPU{
    virtual void operator(){Graph<Tv, Te>* g, int uk, int v){
        选择更好的offer//  更改爸爸
```
