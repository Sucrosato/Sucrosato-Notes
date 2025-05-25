push() pop() top()
LIFO
派生类：以向量或列表为基类
```c++ 
template <typename T> class Stack: public Vector<T> {
```
不选左边为栈顶：

典型应用：
    逆序输出
    递归嵌套
    延迟缓冲
    栈式计算
# 4C 进制转换
# 4D 括号匹配
为什么：方便多符号、甚至自行规定的符号
