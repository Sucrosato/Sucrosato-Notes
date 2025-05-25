`import numpy as np`

```python
class array
    shape =(2, 3)
    
    

```

`A = np.array([1,2,3])
slice is a view, not a copy

`np.random.rand(2,2)    #[0,1)`
`np.random.randn(3,2)    #标准正态分布
`np.random.normal(loc=1,scale=2,size=5) #正态分布`
`np.random.randint(2,10,size=(2,2))`

`a.shape
`a.size
~~`reduce(lambda x,y:x*y , x2.shape) #同size`~~
`a.dtype`

`a.reshape(x, y, z)    #返回新数组`
`a.resize(x, y, z)    #改变原数组`
轴的顺序：越靠内越靠后
`x3[:2,:1,-2:]

`a.flat    #平铺成一维`

broadcast

`np.around(a, 2)    #返回新数组,以及floor, ceil, transpose`
`a.T`
`np.concatenate((x1,x2),axis=1)    #默认0轴`
`np.append(x1, [[7,8,9]],axis = 0)    #默认平铺`
`np.insert(x1,1,[0,0,0],axis=0)    #默认平铺`

`unique`

`@ 矩阵相乘`