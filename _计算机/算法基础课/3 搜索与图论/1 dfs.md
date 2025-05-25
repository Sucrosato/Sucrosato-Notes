- 空间复杂度
    dfs：栈，O(h)
    bfs：队列，O(2^h)
回溯：恢复现场
## 排列数字
深度、回溯
```c++
const int N = 8;
int nums[N];
bool vis[N];
int n;
void dfs(int d)
{
    if (d == n)
    {
        for (int i = 0; i < n; i ++)
        {
            printf("%d ", nums[i]);
        }
        puts("");
        return;
    }
    for (int i = 1; i <= n; i ++)
    {
        if (!vis[i])
        {
            nums[d] = i;
            vis[i] = 1;
            dfs(d + 1);
            nums[d] = 0;
            vis[i] = 0;
        }
    }
    return;
}
```

## n-皇后
剪枝
#### 第一种搜索顺序
与全排序类似
对角线、反对角线占用
#### 第二种
按格子枚举

# 永远注意acwing的调试代码无法接受太长的输入
和注意初始化的时候的索引, 为节省时间复制粘贴可能导致更多的时间浪费


