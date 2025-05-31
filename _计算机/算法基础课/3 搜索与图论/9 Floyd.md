邻接矩阵d(i,j)
三重循环 
    k 1:n
    i 1:n
    j 1:n
        d(i,j) = min(d(i,j), d(i,k) + d(k,j))

- 初始化邻接矩阵，对角线为0, 其他边要设置成无穷大, 然后重边取最小
- 最后邻接矩阵就会变成最短路
- 注意处理不严格的无穷大
## 我的
```c++
#include <iostream>
#include <cstring>
#include <algorithm>
using namespace std;
const int N = 210;
int g[N][N];
int n, m, k;
void floyd()
{
    for (int k = 1; k <= n; k ++)
    {
        for (int i = 1; i <= n; i ++)
        {
            for (int j = 1; j <= n; j ++)
            {
                g[i][j] = min(g[i][j], g[i][k] + g[k][j]); //
            }
        }
    }
}

int main()
{
    memset(g, 0x3f3f3f3f, sizeof(g));
    cin >> n >> m >> k;
    
    for (int i = 1; i <= n; i ++)
    {
        g[i][i] = 0;
    }
    for (int i = 0; i < m; i ++)
    {
        int x, y, z;
        scanf("%d%d%d", &x, &y, &z);
        g[x][y] = min(g[x][y], z);
    }
    floyd();
    for (int i = 0; i < k; i ++)
    {
        int x, y;
        scanf("%d%d", &x, &y);
        if (g[x][y] > 0x3f3f3f3f / 2) puts("impossible");
        else printf("%d\n", g[x][y]);
    }
    return 0;
}
```