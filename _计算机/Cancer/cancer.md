## 1 Understanding the biology of early cancer

一些症状发展成癌症的过程：
    快-慢
    明确-模糊
    微环境：与肿瘤相互作用
    免疫系统

早期癌症模型

## 2 Determining risk of developing cancer

风险评估模型
敏感性、特异性

___
# bpae028
methylation
CpG island promoter hypermethylation/hypomethylation

*为什么用甲基化，有其他办法吗
EMethylNET如何结合了XGBoost和DNN
有哪些优势：robust, generalizable, interpretable, high accuracy
如何验证了他的优越性
*

样本：from TCGA
数据预处理：丢弃噪声、保留染色体、丢弃缺失5%以上值、k-近邻处理5%以下值、处理成M值


## 分类模型和指标
25%测试集
logistic regression, SVM: package sklearn
5 fold
防止过拟合的方法：没懂
XGBoost选择重要的特征，用于输入到DNN
500epoch

