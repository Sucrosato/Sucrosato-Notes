## `vector 变长数组
```c++
a.size() //都有
a.empty() //都有
a.clear()
a.front()
a.back()
a.push_back()
a.pop_back()
a.begin()
a.end()


```
倍增
遍历：
    1. 下标
    2. 迭代器
    3. 范围遍历
判断大小：字典序
#### `pair
.first() .second()
比较：字典序
make_pair( , )
可以随便嵌套
## `string 字符串
size() / length()
empty()
clear()
 +
 substr(int left, int length) //超过的会省略
 
 
## `queue
back() //队尾
push() //队尾
front() //队头
pop() //队头
注意没有clear
## `priority_queue
push()
top()
pop()
**默认大根堆**
小根堆：
    1. 取反插入，取反读出
    2. `priority_queue<int, vector<int>, greater<int>> 
    

## `stack
push()
top()
pop()


## `deque 双端队列
加强版vector
size()
empty()
clear()
front()
back()
push_back()
pop_back()
push_front()
pop_front()
begin() end()
速度稍慢

## `set map multiset multimap 基于红黑树
size() empty() clear(), begin()/end() ++, --
#### `set/multiset
set重复元素会被忽略
insert()
find() //不存在返回end()
count()
erase()
    输入数则删除所有数
    输入迭代器则删除这个迭代器
lower_bound() : >=x O(k + logn)
upper_bound() : > x

#### map/multimap
insert() //插入一个pair
erase() //pair或迭代器
find()
`[] `像数组一样使用 O(logn)
lower_bound()
upper_bound()


## unordered_set unordered_map unordered_multiset unordered_multimap 哈希表
类似，但O(1)
缺点：不支持 lower_bound() upper_bound() ++ --

## `bitset 压位
布尔数组 1/8
`~ &  | ^ >> << == != [] 
`count()
`any()  是否至少有一个1
`none() 是否全为空
`set() 置为1
`set(k, v) 将k位变成v
`reset() 置0
`flip() ~
`flip(k)

`