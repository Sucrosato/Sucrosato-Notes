## 定义
由来自 *字母表 $\Sigma$* 组成的 *有限序列*
往往有：长度>>字母表
## 术语
相等：=
子串：substr(i, k)，从i开始的k个字符
前缀prefix
后缀suffix
`S.substr(i, k) = S.prefix(i + k).suffix(k)
空串：任何串的前缀、后缀、子串
（真）子串、前缀、后缀
## ADT接口
![[Pasted image 20250419095813.png]]
`indexOf(P)` ：寻找子串与目标串相等
