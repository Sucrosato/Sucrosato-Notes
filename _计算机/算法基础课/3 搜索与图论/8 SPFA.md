Bellman-Ford的优化
类似宽搜, 用邻接表存储，用队列遍历, 更新后的边才能更新其他边
实际上也可以用来过正权图
需要避免重复入队列

判断负环：cnt >= n, 所有点都加到初始点集