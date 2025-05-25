## 最短路分类
- 单源最短路
    - 只有正权边
        - 朴素Dijkstra O(n^2)   适合稠密图$m\sim n^2$
        - 堆优化Dijkstra O(mlogn)
    - 存在负权边
        Bellman-Ford O(nm)
        SPFA 一般: O(m) 最坏: O(nm) 有限制条件
- 多源汇最短路
    Floyd O(n^3)
## 朴素Dijkstra
1. 初始化距离, 除初始点以外为无穷
2. 更新距离
稠密图: 邻接矩阵  稀疏图: 邻接表  默认: 有向图

#### 我的
有这么难吗!

```c++
#include <iostream>
#include <algorithm>
#include <cstring>
using namespace std;
const int N = 510;
int edge[N][N], n, m, dis[N];
bool vis[N];
int main()
{
    memset(dis, 0x3f, sizeof(dis));
    memset(edge, 0x3f, sizeof(edge));
    dis[1] = 0;
    cin >> n >> m;
    for (int i = 0; i < m; i ++)
    {
        int x, y, z;
        scanf("%d%d%d", &x, &y, &z);
        edge[x][y] = min(edge[x][y], z);
    }
    for (int i = 0; i < n; i ++)
    {
        int closest = -1, min_dis = 0x3f3f3f3f;
        for(int j = 1; j <= n; j ++)
        {
            if (!vis[j] && dis[j] < min_dis)
            {
                closest = j;
                min_dis = dis[j];
            }
        }
        if (closest == -1) continue;
        vis[closest] = 1;
        for (int j = 1; j <= n; j ++)
        {
            if (edge[closest][j] && !vis[j]){
                dis[j] = min(dis[j], dis[closest] + edge[closest][j]);
            }
        }
        if (vis[n]) break;
    }
    printf("%d", dis[n] == 0x3f3f3f3f ? -1 : dis[n]);
    return 0;
}
```

## 堆优化
直接用priority_queue, 头文件在\<queue\>里, 需要单独定义pair类型的和小根堆, 注意冗余的处理(一个点多次更新只能重复入堆)
```c++
#include <iostream>
#include <algorithm>
#include <cstring>
#include <queue>
using namespace std;
const int N = 2e5;
int head[N], val[N], nxt[N], idx, dis[N], weight[N];
bool vis[N];
typedef pair<int, int> PII;
priority_queue<PII, vector<PII>, greater<PII>> pq;
int n, m;
void add(int x, int y, int z)
{
    val[idx] = y;
    weight[idx] = z;
    nxt[idx] = head[x];
    head[x] = idx ++;
}
int main()
{
    memset(dis, 0x3f, sizeof(dis));
    memset(head, -1, sizeof(head));
    dis[1] = 0;
    pq.push({0, 1});
    cin >> n >> m;
    for (int i = 0; i < m; i ++)
    {
        int x, y, z;
        scanf("%d%d%d", &x, &y, &z);
        add(x, y, z);
    }
    while (!pq.empty())
    {
        int d = pq.top().first, p = pq.top().second;
        pq.pop();
        if (vis[p]) continue;
        vis[p] = 1;
        for (int i = head[p]; i != -1; i = nxt[i])
        {
            if (!vis[val[i]])
            {
                dis[val[i]] = min(dis[val[i]], d + weight[i]);
                pq.push({dis[val[i]], val[i]});
            }
        }
    }
    printf("%d", dis[n] == 0x3f3f3f3f ? -1 : dis[n]);
    cout << endl;
    return 0;
}

```


