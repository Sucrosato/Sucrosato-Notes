## 数字三角形：
处理边界条件：
初始化：\[1, n]\[0, i+1] -> -1e9

Bottom-Up做法
## 最长子序列1
如果要存储最长子序列：记录每个状态从哪个状态转移过来，倒推
## 2
## 最长公共子序列
集合划分后，即便有重叠：由于是求最大值，不影响答案正确
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int f[1001][1001] = {}, n ,m;
    string a, b;
    cin >> n >> m >> a >> b;
    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= m; j++)
        {
            
            f[i][j] = max(f[i][j-1], f[i-1][j]);
            if (a[i-1] == b[j-1]) f[i][j] = f[i-1][j-1] + 1;
            //cout <<f[i][j] << ' ';
        }
        //cout << endl;
    }
    printf("%d", f[n][m]);
    return 0;
}

#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int f[1001][1001] = {}, n ,m;
    char a[1001] = {}, b[1001] = {}; //
    scanf("%d%d", &n, &m);
    scanf("%s%s", a+1, b+1); //
    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= m; j++)
        {
            
            f[i][j] = max(f[i][j-1], f[i-1][j]);//
            if (a[i] == b[j]) f[i][j] = f[i-1][j-1] + 1;//
        }
    }
    printf("%d", f[n][m]);
    return 0;
}
```

## 编辑距离
A T C G G -> A C G G T
A T C G -> A C G G T //栅 n
A T C G G -> A C G G //增 1
A T C G -> A C G G //替换 2
```c++
#include <algorithm>
using namespace std;
int main()
{
    char n[1010] = {}, m[1010] = {};
    int n_len, m_len;
    scanf("%d%s%d%s", &n_len, &n, &m_len, &m);
    int dp[1010][1010] = {};
    for (int i = 0; i <= n_len; i++)
        dp[i][0] = i;
    for (int i = 0; i <= m_len; i++)
        dp[0][i] = i;
    for (int i = 1; i <= n_len; i++)
    {
        for (int j = 1; j <= m_len; j++)
        {
            dp[i][j] = min(dp[i-1][j], dp[i][j-1]) + 1;
            if (n[i-1] == m[j-1])
                dp[i][j] = min(dp[i][j], dp[i-1][j-1]);
            else
                dp[i][j] = min(dp[i][j], dp[i-1][j-1] + 1);
        }
    }
    printf("%d", dp[n_len][m_len]);
}
```
注意索引-1。。。
## 合并石子
拓展：每次可以合并相邻的m堆
规划次序：按照区间长度

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int n, weight[301] = {}, f[301][301] = {}, s[301] = {};
    scanf("%d", &n);
    for (int i = 0; i < n; i ++)
    {
        scanf("%d", weight + i);
        for (int j = i; j < n; j ++) s[j] += weight[i];
    }
    for (int i = 1; i < n; i ++)
    {
        for (int j = 0; j + i < n; j ++)
        {
            int t = 1e9;
            for (int k = j; k < j + i; k ++)
            {
                t = min(f[j][k] + f[k+1][j+i] ,t);
            }
            t += s[j + i];
            if (j > 0) t -= s[j - 1];
            f[j][j+i] = t;
        }
    }
    cout << f[0][n-1];
    return 0;
    
}
```
## 整数划分
#### 完全背包做法
最大价值->选法
#### 另一种
i 恰好表示成 j 个数的和的种类
划分：最小数是否为1
最后求和
