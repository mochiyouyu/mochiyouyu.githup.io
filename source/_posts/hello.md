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
# hexo+Github搭建博客，能访问但无法加载css文件
# 问题：
搭建好hexo后，在本地能够正常访问。

但使用git上传到Github后，发现**能够访问页面但是不能加载CSS样式文件和Jquery文件**

# 最后的解决办法是：
## 1. 修改hexo中 _config.yml 文件：
将root:/  修改为 root:/ xxx.guithub.io 。即 在后面加上Github 主页的仓库名
![](https://img-blog.csdn.net/20181025133243544?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1N0YXJyeWFTa3k=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

## 2. 然后再重新上传
```
    hexo clean
    
    hexo g
    
    hexo d
```
## 详细：

遇到这种能够访问页面但无法加载内容的问题时，首先想到的就是F12，查看问题所在

## 1. F12 ，并刷新页面
![](https://img-blog.csdn.net/20181025131537808?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1N0YXJyeWFTa3k=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

除了前两个请求成功后，以下的请求全报错404。 找到问题就好办了

## 2. 请求失败地址与请求成功地址做对比

* 请求失败404 地址如下图： ![](https://img-blog.csdn.net/20181025131823226?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1N0YXJyeWFTa3k=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
* 第一个请求成功地址如下图： ![](https://img-blog.csdn.net/20181025132303933?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1N0YXJyeWFTa3k=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
* ##### 对比发现
 请求成功地址中的 **space.github.io是 github主页仓库名称。**

而请求失败的地址是：https://starryskyyj.github.io/css/style.css ;该地址并没有访问 仓库名。
* ##### 测试 将仓库名加入到 请求地址中 ![](https://img-blog.csdn.net/20181025132815446?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1N0YXJyeWFTa3k=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
## 3.  修改hexo 中 _config.yml文件

##### 原文件的 root：/  指向的是根目录，在后面添加上 仓库名
     
#####  即修改为 root：/space.github.io

![](https://img-blog.csdn.net/20181025133243544?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1N0YXJyeWFTa3k=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
保存，重新使用git上传到github。

最后访问成功。

![](https://img-blog.csdn.net/20181025133502952?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1N0YXJyeWFTa3k=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

