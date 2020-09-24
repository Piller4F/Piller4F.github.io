# Hexo--->OK  
本次在win10平台使用Hexo搭建本地博客再通过github进行部署,以及使用melody主题进行博客美化,文章中详细的介绍了该博客的搭建过程,希望对大家有帮助。

---
## 一、环境配置  
1. [nodejs下载](http://nodejs.cn/download/)  
</br>
<img src="https://i.loli.net/2020/06/11/GYkM9VuaxS62Lbh.png" height='330px'>
2. nodejs安装
</br>
<img src="https://i.loli.net/2020/06/11/1V4A7JyiUhNtZHQ.png" height='330px'>
全部下一步就可以。
3. win+r 并查看node、npm是否安装完毕
```
node -v
npm -v
```
</br>
<img src="https://i.loli.net/2020/06/11/5KvuQWhCzGwTrlA.png" height='200px'>
4. 由于国内使用npm速度较慢，因此需要使用npm安装cnpm
```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```
5. 使用cnpm安装hexo博客框架
```
cnpm install -g hexo-cli
```
6. 建立本地hexo部署文件(切换自己想要安装的盘符),并进入blog目录。
```
mkdir blog
cd blog
```
7. 初始化自己的本地hexo博客
```
hexo init
```
<img src="https://i.loli.net/2020/06/11/wh3E4nBG82DaTCo.png" height='330px'>
8. 在blog根目录下命名行输入
```
hexo s
```
[本地hexo博客](http://localhost:4000)生成完毕。
9. 现在尝试写自己的第一个博客吧
```
hexo n "我的Hexo博客搭建"
cd source/_posts/
dir
```
我这里的第一个博客当然就是现在正在编辑的“我的Hexo博客搭建”。
10 .重新生成我们的hexo博客
```
cd ../..
hexo clean
hexo g
hexo s
```
查看自己的[本地hexo博客](http://localhost:4000)
</br>
<img src="https://i.loli.net/2020/06/11/gB3x1WXau2NESZI.png" height='330px'>
</br>
可以看到我们的第一个博客建立完毕了。
---
## 二、将自己的博客部署到github
1. 登陆自己的github,New repository。
</br>
<img src="https://i.loli.net/2020/06/11/U1MCbhynXcTr5RQ.png" height='330px'>
</br>
Repository必须是(自己的github用户名).github.io
</br>
<img src="https://i.loli.net/2020/06/11/fjgSiXTosaCt7cV.png" height=''>
2. 进入自己的本地blog目录安装git部署插件
```
cnpm install --save hexo-deployer-git
```
3. 配置自己的本地_config.yml  
用记事本打开就可以,按下面内容进行修改
```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/Piller4F/piller4f.github.io.git 
  branch: master
```
注意repo这行应该为自己的github地址,这里是以我的举例。
4. 将自己的本地博客部署到github  
进入本地blog文件
```
hexo d
```
</br>
<img src="https://i.loli.net/2020/06/11/gidvRZMOh51ctx6.png" height='330px'>
5. 在浏览器中输入网址
```
以我自己建立的博客为例
piller4f.github.io
```
</br>
<img src="https://i.loli.net/2020/06/11/OiIYyzkuF9QNAs3.png" height='330px'>
---
## 三、更换我们的hexo主题
我想给我的博客使用melody主题，这个主题简约好看。
</br>
<img src="https://i.loli.net/2020/06/11/HfKarQ1e9tXWlRD.png" height='330px'>
</br>
[官方melody使用教程](https://molunerfinn.com/hexo-theme-melody-doc/zh-Hans/quick-start.html)
1. 进入本地blog文件安装melody
```
git clone -b master https://github.com/Molunerfinn/hexo-theme-melody themes/melody
npm install hexo-renderer-jade hexo-renderer-stylus
```
</br>
<img src="https://i.loli.net/2020/06/11/SC8Qw9f6HUtzZAe.png" height='330px'>
2. 修改配置文件_config.yml  
```
# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: melody
```
3. 重新生成hexo
```
hexo g
hexo s
```
查看下本地hexo博客，如果有奇怪错误
```
hexo clean
```
部署我的博客
```
hexo d
```
如果出现部署失败时,重新安装git部署插件,再进行部署
```
npm install hexo-deployer-git –save
```
最终的效果
</br>
<img src="https://i.loli.net/2020/06/11/FZehgUsmISYM6OP.png" height='330px'>
---
## 四、melody主题配置
1. 将```blog\themes\melody\_config.yml```复制并更名到```F:\blog\source\_data\melody.yml```
2. 配置melody.yml([配置方法](https://molunerfinn.com/hexo-theme-melody-doc/zh-Hans/theme-config.html#%E8%87%AA%E5%AE%9A%E4%B9%89%E4%B8%BB%E9%A2%98%E8%89%B2))  
这里我只展示我修改的部分
 
```
# _config.yml
# Site
title: 死磕少年
author: Piller4F
language: zh-Hans

```

```
# melody.yml
# Main menu navigation
menu:
  主页: /
  归档: /archives
 # 标签: /tags
 # 分类: /categories
 # 关于作者: /about
 #XXX: /xxx 
avatar: https://i.loli.net/2020/04/03/NHGA4cXkeSMDKml.png
top_img: https://i.loli.net/2020/06/11/gMshtI2zZdwBjev.png # false or url of img
footer_custom_text: 欢迎访问
fireworks: true
```

---
## 五、使用Gitalk为博客添加评论功能
1. 什么是Gitalk?  
Gitalk是一个基于GitHub Issue和Preact开发的评论插件  
可以使用github直接登陆，并支持多种语言，支持Markdown语法等。  
2. Gitalk安装
```
npm i --save gitalk
```
3. 申请一个**GitHub Application**[点我。](https://github.com/settings/applications/new)
```
依次为
随便
博客地址
随便
博客地址
```
<img src="https://i.loli.net/2020/06/11/OsnWqGEao7TuiLM.png" height='330px'>
</br>
Client ID、Client Secret复制
</br>
<img src="https://i.loli.net/2020/06/11/vYcsJLj3gqNR7Fx.png" height=''>
4. 修改melody.yml
```
gitalk:
  enable: true
  client_id: **************         #输入复制的
  client_secret: **************
  repo:  piller4f.github.io         #博客地址
  owner: Piller4F                   #github用户名
  admin: Piller4F                   #github用户名
```
5. 将hexo部署到github后，登陆就可以用了  
![](https://i.loli.net/2020/06/11/s1tpNhuKR5Uw9dE.png)

---
## 六、Addthis分享功能
1. [Addthis官网](https://www.addthis.com/)
2. 配置分项分格
3. 点击右上角Get The Code  
![](https://i.loli.net/2020/06/11/NX9OUmg43foljsA.png)
4. 配置**melody.yml**
```
addThis:
  enable: true
  pubid: ra-5dd8f37b7cd00be8
```

---
## 七、为自己的博文添加Live2D动画模型挂件
1. 安装Live2D模块
```
npm install --save hexo-helper-live2d
```
最好用cnpm比npm快了不知多少(当然你得装cnpm)
```
cnpm install --save hexo-helper-live2d
```
2. [模型下载地址](https://github.com/xiazeyu/live2d-widget-models)下载packages文件就可以
3. [模型预览](https://huaji8.top/post/live2d-plugin-2.0/)
4. 将packages中的所有文件拷贝到node_moduels目录下
5. 打开博客根目录的_config.yml,添加如下内容:
```
# live2D 模型
live2d:
  enable: true
# enable: false
  scriptFrom: local # 默认
  pluginRootPath: live2dw/ # 插件在站点上的根目录
  pluginJsPath: lib/ # 脚本文件相对与插件根目录路径
  pluginModelPath: assets/ # 模型文件相对与插件根目录路径
  model:   
    use: live2d-widget-model-hijiki # 下载的动画模型名称
    display:
    superSample: 2
    width: 210
    height: 420
    position: right # 模型显示在网页上的位置
    hOffset: -20
    vOffset: -20
```
![黑猫来也](https://i.loli.net/2020/06/15/Y8rxXNHQds5pPOG.png)