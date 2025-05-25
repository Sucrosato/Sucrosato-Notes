从1开始
神奇的写法：
```c++
#include <iostream>
using namespace std;
const int N = 1e5 + 10, M = 1e6 + 10;
char ptn[N], s[M];
int nxt[N];
int main()
{
    int n, m;
    cin >> n >> ptn + 1 >> m >> s + 1;
    for (int i = 2, j = 0; i <= n; i ++)
    {
        while (j && ptn[i] != ptn[j + 1]) j = nxt[j];
        if (ptn[i] == ptn[j + 1]) j ++;
        nxt[i] = j;
    }
    for (int i = 1, j = 0; i <= m; i ++)
    {
        while (j && s[i] != ptn[j + 1]) j = nxt[j];
        if (s[i] == ptn[j + 1]) j ++;
        if (j == n) printf("%d ", i - n);
    }
    return 0;
}
```
