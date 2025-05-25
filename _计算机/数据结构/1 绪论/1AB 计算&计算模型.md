# 计算
算法的性质
    输入
    输出
    正确性
    确定性：任一算法可视作基本操作的序列
    可行性：每一基本操作可实现且在常数时间内完成        *大象赶到冰箱里*
    有穷性：对任何输入可通过有穷次基本操作得到输出
        Hailstone sequence 既没有反例，也没有证明
        程序$\neq$算法
好算法
    **正确**
        多种程度的正确...
    健壮
    可读
    **效率**
        DSA: Data Structure & Algorithm

# 计算模型
*Lord Kelvin*
正确性 & 成本（**时间**，空间）
成本
    $T_A(P)$ 
    实例太多：划分等价类
    $->T_A(n)或T(n)$
    最坏情况：$$T(n)=max\{T(p)||P|=n\}$$
# 理想模型
实验法：不可靠
理想平台：用抽象平台中执行的 *基本操作次数* 来评估效率
    图灵机模型
        Tape
        Alphabet & Cell
        Head         读写头
        State
        Transition Function 传递函数 `(q, c; d, L/R, p)`
            `q` 读写头所处的状态
            `c` 读写头当前位置cell的字符
            `d` 修改后的新字符
            `L/R` 向左或向右移动1个cell
            `p` 转换成的状态 `h`则停机
         示例：非负整数加1
    RAM模型
        Random Access Machine
        R\[i\] 无穷个寄存器```
        R[i] <- c
        R[i] <- R[j]
        R[i] <- R[R[j]] & R[R[j]] <- R[i]
        R[i] <-  R[j] + R[k]
        IF R[i] = 0
        GOTO 1
        STOP
        ```
        示例：向下取整的除法```
            0    R[3] <-  1
            1    R[0] <- R[0] + R[3]
            2    R[0] <- R[0] - R[1]
            3    R[2] <- R[2] + R[3]
            4    IF R[0] > 0 GOTO 2
            5    R[0] <- R[2] - R[3]
            6    STOP```
            
