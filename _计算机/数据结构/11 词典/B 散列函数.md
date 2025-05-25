不可能是单射
尽可能降低概率
预案：及时排解冲突
#### 散列函数的好
确定 determinism
快速 efficiency
满射 surjection
均匀 uniformity : 避免 clustering

蝉的哲学：选择素数，增加均匀性
一阶均匀：邻近仍然邻近、0一定对应0

#### MAD 
`hash(key) = ((a * key) + b) % m`
step + offset -> low uniformity
有时相反，需要局域性（高维几何）
    Locality-Sensitive Hashing
有时相反，需要将低维映射到高维（密码学）

#### 更多散列函数
平方取中（使各数位贡献接近）
折叠：按位相加
按位异或
伪随机数法：$hash(key)=rand(key)=[rand(0)\times a^{key}]\%m$
    可移植性差
多项式：
    字符串关键码->n次多项式的系数
    近似：32位的后5位挪到开头
    

