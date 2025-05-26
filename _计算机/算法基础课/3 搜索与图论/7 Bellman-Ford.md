很简单 随便存边 struct

n次遍历所有边:
    `dist[b] = min(dist[b], dist[a] + w)`
要没有负权回路(或不在路径当中)

遍历k次代表经过不超过k条边的dist,所以可以找负环(但一般不用)
## 有边数限制的最短路径
注意!:
1. 不要判断0x3f, 因为负权边会让他小于0x3f, 判断初始化大值的一半
2. 更新的时候**只有后半**用备份, 防止串联和覆盖
    `dist[b] = min(dist[b], dist_bac[a] + w)`
```c++
#include <iostream>
#include <cstring>
#include <algorithm>
using namespace std;
const int N = 1e4 + 10, M = 5e2 + 10;
int edge[N][3], n, m, k, dis[M], dis_bac[M];
int main()
{
    memset(dis, 0x3f, sizeof(dis));
    dis[1] = 0;
    cin >> n >> m >> k;
    for (int i = 0; i < m; i ++)
    {
        scanf("%d%d%d", &edge[i][0], &edge[i][1], &edge[i][2]);
    }
    for (int i = 0; i < k; i ++)
    {
        memcpy(dis_bac, dis, sizeof(dis));
        for (int j = 0; j < m; j ++)
        {
            dis[edge[j][1]] = min(dis[edge[j][1]], dis_bac[edge[j][0]] + edge[j][2]);
        }
    }

    if (dis[n] > 0x3f3f3f3f / 2) printf("impossible");
    else printf("%d", dis[n]);
    return 0;
}
```
    