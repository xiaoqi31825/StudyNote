## 常用指令
```

```



## 常见问题
### 远程仓库误推送了.idea文件夹
1. 删除远程仓库中的.idea文件夹
```shell script
git rm -rf --cached .idea
```
2. 提交注释
```shell script
git commit -m '忽略误提交的.idea文件夹'
```
3. 推送到远程仓库
```shell script
git push -u origin 分支名
```
4. 在.gitignore文件中加上(排除.idea文件夹)
```
**/.idea
```