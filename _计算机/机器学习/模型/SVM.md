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
params are  {'kernel': 'rbf', 'tol': 0.001, 'gamma': 'scale', 'probability': True}
[1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1
 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1
 1 1 1 1 1 1 0 1 1 1 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 1 1 0 1 1
 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]
[1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1]
d:\App\ANACONDA\Lib\site-packages\sklearn\metrics\_classification.py:1531: UndefinedMetricWarning: Precision is ill-defined and being set to 0.0 in labels with no predicted samples. Use `zero_division` parameter to control this behavior.
  \_warn_prf(average, modifier, f"{metric.capitalize()} is", len(result))
Accuracy: 
0.937007874015748
Conf mat:
[[  0   8]
 [  0 119]]
Precision:  [0.         0.93700787]
Recall:  [0. 1.]
F1:  [0.         0.96747967]
Matthews Correlation Coeficient:  0.0
roc_auc for each class:  [1. 1.]
        name                    values
0   Accuracy                  0.937008
1  Precision  [0.0, 0.937007874015748]
2     Recall                [0.0, 1.0]
3         f1  [0.0, 0.967479674796748]
4        mcc                       0.0
5    roc_auc                [1.0, 1.0]
num classes is:  2
     Normal          
0.0   0.000       NaN
0.0   0.125       NaN
0.0   1.000       NaN
1.0   1.000       NaN
0.0     NaN  0.000000
0.0     NaN  0.008403
0.0     NaN  1.000000
1.0     NaN  1.000000
            Normal     
1.000000  0.062992  NaN
1.000000  0.063492  NaN
1.000000  0.064000  NaN
1.000000  0.064516  NaN
1.000000  0.065041  NaN
...            ...  ...
0.033613       NaN  1.0
0.025210       NaN  1.0
0.016807       NaN  1.0
0.008403       NaN  1.0
0.000000       NaN  1.0

[256 rows x 2 columns]
![[Pasted image 20250401112108.png]]