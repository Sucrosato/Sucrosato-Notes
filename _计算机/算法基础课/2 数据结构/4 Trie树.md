高效存储和查找字符串集合的数据结构
二维数组模拟26叉树，对应一维数组存储次数
## 我的
```c++
#include <iostream>
using namespace std;
const int N = 1e5 + 10;
int son[N][26], cnt[N], idx;
void ins(char s[])
{
    int p = 0;
    for (int i = 0; s[i]; i ++)
    {
        int c = s[i] - 'a';
        if (!son[p][c]) son[p][c] = ++idx;
        p = son[p][c];
    }
    cnt[p] ++;
}
int que(char s[])
{
    int p = 0;
    for (int i = 0; s[i]; i ++)
    { 
        int c = s[i] - 'a';
        if (!son[p][c]) return 0;
        p = son[p][c];
    }
    return cnt[p];
}
int main()
{
    int n;
    cin >> n;
    char s[N] = {};
    while (n--)
    {
        char op;
        cin >> op >> s;
        if (op == 'I') ins(s);
        else printf("%d\n", que(s));
    }
    return 0;
}

```