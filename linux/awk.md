```bash
# 统计文件行数
awk '{print NR}' git.md | tail -n1
awk 'END{print NR}' git.md

wc -l git.md | awk '{print $1}'
cat git.md | wc -l
```
