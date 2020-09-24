# SourceTree的简单应用
这里简单的介绍了SourceTree的部分使用，博客内容会随着博主的理解加深而不断更新。

---
## SourceTree简介
```
SourceTree是一个拥有图形界面Git工具，它可以操作任何Git库，把以往使用的Git命令通过GUI的形式使用，这样更加容易上手。
```
---
## 下载并安装SourceTree
1. [下载地址](https://www.sourcetreeapp.com/)。
2. 安装就一直next。
---
## SourceTree的简单使用
### 分支的创建与合并
![](https://i.loli.net/2020/06/15/LVcYHMEThiGRnwl.png)
1. 添加本地库(本地库的建立可以看我之前的Git教程)。
![](https://i.loli.net/2020/06/15/YkJ23VPTBAcqG5r.png)
2. 创建一个分支
![](https://i.loli.net/2020/06/15/QY86itUku7hgyqb.png)
3. 修改文件
![](https://i.loli.net/2020/06/15/nQa7ToBMUNztih3.png)
```C++
#include <iostream>
using namespace std;
int main () {
	cout<<"First modify"<<endl;
	cout<<"Dev branch modify"<<endl;
	cout<<"hello world"<<endl;
	cout<<"Zhuang"<<endl;
	cout<<"SourceTree"
	return 0;
}
```
4. 先添加暂存区再提交
![](https://i.loli.net/2020/06/15/6TIF8hvwDxE9ypB.png)
![](https://i.loli.net/2020/06/15/hMcgWlL1m56aGjQ.png)
重复几次上述操作
5. 如现在需要将`dev`合并到`master`,点击合并
![](https://i.loli.net/2020/06/15/mQcVC1Eu7GbRylP.png)
![](https://i.loli.net/2020/06/15/8WPmZCHnUTSElvc.png)
![](https://i.loli.net/2020/06/15/OlUaCYIkMtLyQ3B.png)
6. 推送至远程代码库
![](https://i.loli.net/2020/06/15/XjEDzqsAYiU4cKp.png)
![](https://i.loli.net/2020/06/15/vVSudqiJ7oBkXy1.png)
### 添加标签
![](https://i.loli.net/2020/06/15/ulJGB9ChOWRKy6r.png)
![](https://i.loli.net/2020/06/15/KUNqCrLdo63Qz8j.png)