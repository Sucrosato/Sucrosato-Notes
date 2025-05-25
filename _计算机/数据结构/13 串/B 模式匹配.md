*Pattern matching*
    detection -> bool
    **location -> \***
    counting -> int
    enumeration -> int, *
## 算法的评估
成功：随机取子串匹配，取平均
失败：随机串匹配，平均
## 蛮力匹配
match1()
    双指针，分别指示i,j的进度，失败回退；查找失败返回超出可能的索引值
match2()
    for for
O(n\*m)
字母表越小、m越长->越坏
