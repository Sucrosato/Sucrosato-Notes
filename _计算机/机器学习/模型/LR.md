12
running

Getting values and diagnoses from: 
../data_preprocessing/dataset/pandas/m_values/TCGA-LUAD.csv
../data_preprocessing/dataset/pandas/diagnoses/TCGA-LUAD.csv
m_value and diagnoses shapes:
(262616, 507)
(507,)
m values train, m values test, diagnoses train, diagnoses test shapes:
(380, 262616) (127, 262616) (380,) (127,)
[1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1
 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1
 1 1 1 1 1 1 0 1 1 1 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 1 1 0 1 1
 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]
[1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1
 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1
 1 1 1 1 1 1 0 1 1 1 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 1 1 0 1 1
 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]
Accuracy: 
1.0
Conf mat:
[[  8   0]
 [  0 119]]
Precision:  [1. 1.]
Recall:  [1. 1.]
F1:  [1. 1.]
Matthews Correlation Coeficient:  1.0
roc_auc for each class:  [1. 1.]
        name      values
0   Accuracy         1.0
1  Precision  [1.0, 1.0]
2     Recall  [1.0, 1.0]
3         f1  [1.0, 1.0]
4        mcc         1.0
5    roc_auc  [1.0, 1.0]
num classes is:  2
          Normal          
0.000000   0.000       NaN
0.000000   0.125       NaN
0.000000   1.000       NaN
0.966387   1.000       NaN
1.000000   1.000       NaN
0.000000     NaN  0.000000
0.000000     NaN  0.033613
0.000000     NaN  1.000000
1.000000     NaN  1.000000
            Normal     
1.000000  0.062992  NaN
1.000000  0.065041  NaN
1.000000  0.065574  NaN
1.000000  0.066116  NaN
1.000000  0.066667  NaN
...            ...  ...
0.058824       NaN  1.0
0.050420       NaN  1.0
0.042017       NaN  1.0
0.033613       NaN  1.0
0.000000       NaN  1.0

[250 rows x 2 columns]
![[Pasted image 20250401112850.png]]