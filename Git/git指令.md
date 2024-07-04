## 常用指令
```

```



## 常见问题
### 远程仓库误推送了.idea文件夹
#### 解决方法-步骤： 
1.删除远程仓库中的.idea文件夹
```shell script
git rm -rf --cached .idea
```
2.提交注释
```shell script
git commit -m '忽略误提交的.idea文件夹'
```
3.推送到远程仓库
```shell script
git push -u origin 分支名
```
4.在.gitignore文件中加上(排除.idea文件夹)
```pydocstring
**/.idea
```

### 推送代码报错:Failed to connect to github.com port 443 after 21090 ms: Couldn't connect to server
#### 原因:
可能是因为开启了某些网络代理(如翻墙软件)导致的,关闭网络代理后重新推送。