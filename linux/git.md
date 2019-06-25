- 初始化git仓库，关联远程仓库
```bash
# 初始化repository
git init

# add远程仓库
git remote add origin git@github.com:wangller/blogs.git

# 关联远程仓库
git push -u origin master

# push到远程仓库
git push
```
- log
```bash
# 打印commit日志
git log --oneline

# 同上
git log --pretty=oneline --abbrev-commit
```