## 常见问题

### 1、远程仓库误推送了.idea文件夹
#### 解决步骤
1)删除远程仓库中的.idea文件夹
```shell script
git rm -rf --cached .idea
```
2)提交注释
```shell script
git commit -m '忽略误提交的.idea文件夹'
```
3)推送到远程仓库
```shell script
git push -u origin 分支名
```
4)在.gitignore文件中加上(排除.idea文件夹)
```python
**/.idea
```

### 2、push报错: Failed to connect to github.com port 443 after 21090 ms: Couldn't connect to server
#### 原因
可能是因为开启了某些网络代理(如翻墙软件)导致的,关闭网络代理后重新推送。


### 3、git clone SSH项目链接报错: Failed to connect to github.com port 443: Connection timed out
#### 原因
有多种原因，具体原因暂时不确定。
#### 解决方法
方法1: 把SSH链接换成HTTPS链接(也许会有其他问题--不推荐)
