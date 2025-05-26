- 什么是数据增强
- 为什么要进行数据增强
- 数据增强的一些示例
    单张图片
        翻转
        噪声
        切方块
    多张图片
        粘贴
        马赛克
        MixUp
            $\lambda$
            降低了错误率
            一些方向
## more reasonable $\lambda$
#### Area depenency
cut-out -> cut-mix
attentive-cutmix
预训练模型->热力值（顺便说明了lambda）
    区别
    改进了一些缺陷
引出了：
#### Significance dependency
$\rho_a,\rho_b$
->非对称粘贴，增加随机性
Transmix
Saliencymix
    对显著/非显著选择的解释
## more reasonable $\lambda$ & location
