- 初始化git仓库，关联远程仓库
```bash
# 初始化repository
git init

# add远程仓库, 和直接修改.git/config文件效果一致
git remote add origin git@github.com:wangller/blogs.git
# 添加另一个地址, 可同时push到两个
git remote set-url --add origin http://localhost:8092/blogs.git

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