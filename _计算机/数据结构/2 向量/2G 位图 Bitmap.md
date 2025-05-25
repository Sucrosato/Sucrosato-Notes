重点：数据可能的范围是有穷的，可以给可能出现的每个数据一个bit来存储有/无
`k/8 == k>>2`
`k%8 == k&0x07`
bit-byte, offset 
```c++
bool test(int k) { return M[k>>3] & (0x80 >> (k & 0x07)); }
void set(int k) // |=
void clear(int k) // & 0
```
## 应用：
去重（小集合+大数据）
筛法求素数：
`void  Ere
    *pupupu


## 快速初始化
Hopcroft校验环：
Bitmap B,int F,int T
防止巧合：只算已经注册的

