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

