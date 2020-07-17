---
title: hello
date: 2020-07-17 13:55:42
tags:
---
## 通过Hexo发布的第一个微博

```
  hexo init <folder>
   初始化一个文件夹
    cd <folder>
   进入创建的文件夹
  npm install hexo-deployer-git --save
   安装发布命令，每次创建新的文件夹都需要执行
    
```
### Hexo命令的执行

``` 
    hexo clean 清除缓存能让发布的博客快速生效
    hexo generate 生成新的静态文件 (hexo g)
    hexo deploy 把生成的文件部署到博客上，(hexo d)
```

``` 
   hexo new 博客名 利用本命令可以创建一个md文件
   git clone --depth 1 git@github.com:iissnan/hexo-theme-next.git themes/netxi
   下载新的主题
    git checkout -b dev 创建新的分支，并切换到它
```
### 解决git push失败问题failed to push some refs to 'git@github.com:lXXX/XXX.git'
 ![](https://img-blog.csdnimg.cn/20190813161313331.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xpdWhwMTIz,size_16,color_FFFFFF,t_70)
 
 本人遇到这个问题去网上搜索了办法，原因是本地仓库与远程仓库产生冲突，解决办法如下：
 
 1 . 若此方法好使，请忽略方法2.
 
``` 
  git pull origin master 
```
2. 尝试了方法1.并没有作用，再尝试此方法

```
    git pull --rebase origin master
```

3. 然后再重新push到远程仓库：

```
    git push origin master
```