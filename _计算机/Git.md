![[Git-Cheet-Sheet-ByGeekHour.png]]![[Pasted image 20250318153825.png]]![[Pasted image 20250318153840.png]]![[Pasted image 20250318153927.png]]安装
git -v
git config # 配置邮箱名字

repository(Repo)

git init
git clone

git status
git add \<file>  # 通配符
git commit -m \<info>
git log --oneline
#### 远程仓库
设置ssh密钥（本地、github的公钥）
ssh-keygen -t rsa -b 4096
git push
git pull

## reset
git reset --soft/hard/mixed HEAD^
git reflog

## dif
git diff
git diff HEAD //工作区和版本区
git diff --cached //
git diff \<id1> \<id2>
HEAD~n //~或^n：上n(1)个版本

## git太慢
~~git config --global http.proxy http://127.0.0.1:7890; git config --global https.proxy https://127.0.0.1:7890
7890是clash的端口~~
#### 适用于ssh传输:
以 Windows 10 操作系统为例：
1. 右键点击 "Git Bash here"，打开一个命令行窗口
2. 编辑 ssh_config ： vim /etc/ssh/ssh_config
3. 搜索 GSSAPIAuthentication 找到该配置项
4. 配置禁用 GSSAPI 校验：默认使用 # 号注释掉了，去除行首注释或者新增 GSSAPIAuthentication no，然后保存退出
5. 使用 ssh 方式再次操作 git 项目，速度飞快
[https://www.jianshu.com/p/7660177125a1]

