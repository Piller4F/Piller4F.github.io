# git的学习
初次接触git,对git的使用进行简单梳理。

---

## Git简介
Git是目前世界上最先进的分布式版本控系统。  
那么什么是版本控制系统呢？？？  
比如说我们现在写一个学生管理系统，当我们每完成一个功能时，可以说当前的代码的bug率很低，  
现在不应该时继续去完成其它功能，而是将当前项目做备份，以免自己在后续的功能增加中修改了  
之前的代码后发生的错误，如果没有备份，修改起来比较繁琐，这会极大的影响开发效率。  
</br>
![](https://i.loli.net/2020/06/11/upXMrvCQVq4WtHm.png)
</br>
说到版本控制系统这里就得稍微介绍下SVN
![](https://i.loli.net/2020/06/11/vGtB32Iuk9XZS47.png)  
每个开发者可以直接连接服务器，然后在本地修改，最好commit到SVN服务器上。这样造成的问题就  
是，通常本地只是缓存一个小版本，版本的历史信息都在服务器上，一旦离开服务器本地就不能够追  
踪代码版本。并且当项目过于庞大时会显得更加杂乱。
![](https://i.loli.net/2020/06/11/IcfiOZatgs857D2.png)
可以看到分布式的结构，我们的本地可以pull下完成的版本库，并且可以制定一个leader端，可以很  
方便的提供给大家交换修改，当然因为每个人都有完整的库，因此任意两个人都可以进行修改，断网时  
也会存在历史版本在个人终端中。

---

## git的安装
1. [Git官网下载](http://git-scm.com/)
2. 一路next就行。
3. win+r 
```
git --version
```
提示版本号则安装完成  
4. github注册账号，并新建一个repository  
![](https://i.loli.net/2020/06/11/Q7EbuqMyrgLJ8mf.png)  
5. 将本地git和github连接起来
桌面右击Git Bash Here
```
ssh-keygen
```
按3下回车，进入**C:\Users\Piller4F\\.ssh**记事本打开**id_rsa.pub**复制，打开自己的github  
![](https://i.loli.net/2020/06/11/PqQgIa539JEnfGj.png)  
复制即可

---
## git的基本操作
### 创建版本库
1. 创建一个代码库
找一个合适的地方建立文件夹
```
mkdir FirstPractice
cd FirstpPractic
pwd
```
2. 使用```git init```命令将该目录变为Git管理的仓库
```
git init
```
此时Git仓库为一个空的仓库，你会发现生成了一个```.git```的目录，这个目录就是Git来跟踪管理版本库。  
3. 我们编辑一些文件例如```main.cpp```内容如下。
```C++
#include <iostream>
using namespace std;  
int main () {
	cout<<"hello world"<<endl;
	return 0;
}
```
4. 使用```git add```命令，将文件加入仓库。
```
git add main.cpp
```
5. 使用```git commit```命令，将文件提交到仓库，```-m```后面输入的是本次commit提交的说明，虽然不是必须的，但是有了备注之后更加方便其它人寻找改动记录。  
```
git commit -m "first initial"
```
那么为什么我们需要添加两次到仓库呢，其实使用```add```命令时会将文件发送到一个暂存区的地方，暂存区可以多次被添加文件，使用```commit```后会将暂存区所有的文件都导入到版本库中，后续会说道这样做的优点。  
6. 我们现在修改```main.cpp```中的代码。用git中的vim直接进行操作。将```main.cpp```改为如下：  
```C++
#include <iostream>
using namespace std;  
int main () {
	cout<<"First modify"<<endl;
	cout<<"hello world"<<endl;
	return 0;
}
```
7. 然后运行```git status```看看结果：
```
git status
```
8. 发现有红色标记```main.cpp```被修改了。红色是表明没有被提交，我们使用```git diff```看看修改了什么：  
```
git diff
```
9. 然后我们通过刚才的方法先```add```后```commit```：
```
git add main.cpp
git commit -m "add First modify"
```
### Git的版本控制功能---回退  
- 版本1：
```C++
#include <iostream>
using namespace std;
int main () {
	cout<<"hello world"<<endl;
	return 0;
}
```
- 版本2：
```C++
#include <iostream>
using namespace std;
int main () {
	cout<<"First modify"<<endl;
	cout<<"hello world"<<endl;
	return 0;
}
```
我们在实际工作中看不出来那个版本修改了什么，但在Git中，我们使用```git log```命令查看：  
```
git log
```
```
commit 52ad3a63045092cefd1e6eb8ef3e5ac2d84649f6 (HEAD -> master)
Author: Shi Guoqiang <piller4f@163.com>
Date:   Fri Jun 12 21:28:10 2020 +0800
    add First modify
commit cfb32fbb5d91b5b767fc94095f87c6e5ce123dc4
Author: Shi Guoqiang <piller4f@163.com>
Date:   Fri Jun 12 21:18:42 2020 +0800
    first initial
```
可以看到第一次我们```first inital```第二次是```add First modify```  
信息较多，因此我们可以使用
```
git log --pretty=oneline
```
```
52ad3a63045092cefd1e6eb8ef3e5ac2d84649f6 (HEAD -> master) add First modify
cfb32fbb5d91b5b767fc94095f87c6e5ce123dc4 first initial
```
可以看到前面那么一串的是commit的版本号。那当我们需要回退到上一个版本怎么做呢？？？
```
git reset --hard HEAD^
HEAD is now at cfb32fb first initial
```
可以看到其中```cfb32fb```不就是我们第一次版本的版本号的前几个字符。然后打开我们的```main.cpp```发现变为如下：
```C++
#include <iostream>
using namespace std;
int main () {
	cout<<"hello world"<<endl;
	return 0;
}
```
使用```git log```看看本地版本库状态。
```
commit cfb32fbb5d91b5b767fc94095f87c6e5ce123dc4 (HEAD -> master)
Author: Shi Guoqiang <piller4f@163.com>
Date:   Fri Jun 12 21:18:42 2020 +0800
    first initial
```
那么现在我想后悔了，准备恢复回去怎么办？？？使用```git reflog```
```
cfb32fb (HEAD -> master) HEAD@{0}: reset: moving to HEAD^
52ad3a6 HEAD@{1}: commit: add First modify
cfb32fb (HEAD -> master) HEAD@{2}: commit (initial): first initial
```
可以看到我们```add First modify```版本号```52ad3a6```使用```git reset```
```
git reset --hard 52ad3a6
HEAD is now at 52ad3a6 add First modify
```
这里涉及到一个概念```HARD```它其实是一个指针，用于定位当前版本，因此只要有```commit_id```我就可以到任何版本。  
### 工作区和暂存区的概念 
- 工作区  
我们的```FirstPrectice```就是我们的工作区
- 版本库  
工作区中又一个目录```.git```这个是我们Git的版本库。其中最重要的```stage```(暂存区)，以及Git为我们自动创建的一个分支```master```和一个指针```HEAD```。
我们知道git在添加文件时有两步骤：  
第一步使用```git add```将文件添加入暂存区。  
第二步使用```git commit```将暂存区中的所有文件提交到当前分支。
因此将需要修改所有文件放入暂存区，然后一次性的将所有的修改提交到当前分支。  
### 撤销修改
我们将```main.cpp```修改为如下
```C++
#include <iostream>
using namespace std;
int main () {
	cout<<"你个麻瓜！！！"<<endl;
	cout<<"First modify"<<endl;
	cout<<"hello world"<<endl;
	return 0;
}
```
可以看到不知道怎么回事心情不好，暴躁的写了一句“你个麻瓜”。当然如果你把这个交了，估计会被头头问话了。因此这是我想撤销我的修改。  
使用
```
git checkout --main.cpp
```
此时你发现ok了，你在工作区中的修改被恢复。  
那现在问题又来了，我将```main.cpp```给```add```了，现在在暂存区里面。  
使用```git reset HEAD filename```将当前暂存区清除，此时在和之前一样删除就可以了。
```
git reset HEAD main.cpp
git checkout -- main.cpp
```
### 删除文件
当我们讲一个文件提交进版本库，为了保证工作区和版本库中的一致性，不可以直接在工作区删除文件同样需要使用```git```命令，并提交版本库。
先添加
```
git add file.md
git commit -m "add file.md"
```
再删除
```
git rm file.md
git commit -m "rm file.md"
```
### 部署远程仓库  
在Git安装的时候已经配置了SSH加密，并建立了gitbub仓库，这里不再赘述。
将github上了仓库和本地仓库做关联。
```
git remote add origin https://github.com/Piller4F/FirstPractice.git
```
把本地内容推送到远程库上：
```
git push origin master
```
这时候可能会出现错误  
```
error：failed to push some refs to......
```
由于github在建立代码库时选择生成了```README.md```导致远程库不一致。
```
git pull -rebase origin master
```
这里就将远程库和本地库进行了统一
```
git push origin master
```
将代码推到远程库
### 从远程库进行克隆  
找一个自己心仪的文件夹
```
git clone https://github.com/Piller4F/FirstPractice.git
```
### 创建与合并
在Git中```master```为主分支，而```HEAD```指向```master```表明，```HEAD```指向的是目前正操作的对象。而当我们创建一个新的分支的时  
候例如```dev```Git则新建了一个指针叫```dev```再把```HEAD```指向```dev```上，因此目前的操作对象就成了```dev```这个路线。到了合并的时  
候，只需要将```master```指向的```dev```就完成了合并。合并完成后，我们还可以删除```dev```分支。  
```
git checkout -b dev
```
```git checkout```命令加上```-b```表示创建并切换，等同于：
```
git branch dev
git checkout dev
```
然后查看当前分支情况。
```
git branch
```
我们可以看到，当前分支前面会标有一个```*```号，然后我们来修改```main.cpp```。
```C++
#include <iostream>
using namespace std;
int main () {
        cout<<"First modify"<<endl;
        cout<<"Dev branch modify"<<endl;
        cout<<"hello world"<<endl;
        return 0;
}
```
然后添加并提交
```
git add main.cpp
git commit -m "Dev branch modify"
```
现在我们可以切换回```master```分支，将dev合并到```master```分支上:
```
git checkout master
git merge dev
```
### 分支的删除
删除```dev```分支
```
git branch -d dev
```
目前就只剩下```master```唯一的一个分支了，切换分支还有一种方法就是```git switch```命令
```
git branch dev
git switch dev
```
### 创建标签  
标签对于开发者来说非常实用
```
git switch master
git tag v1.0
```
如果我现在需要给之前版本加标签呢？
```
git log --pretty=oneline --abbrev-commit
git tag v0.9 de7ada0
```
显示标签信息
```
git show v1.0
```
还可以加入带有说明的标签
```
git tag -a v0.1 -m  "First" b5691ef
```
### 标签的操作
如果需要删除标签
```
git tag -d v0.1
```
如要推送某个标签的远程
```
git push origin v1.0
```
一次性推送全部本地标签
```
git push origin --tags
```
如果要远程标签，则应该先本地删除
```
git tag -d v0.9
```
然后从远程删除
```
git push origin :refs/tags/v0.9
```
