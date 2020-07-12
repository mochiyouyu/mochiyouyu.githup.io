## 今天学习了MarkDown
MarkDown是一种超文本语言，今天我第一次学习了他。


   `hello MarkDown!`


接下来我还会学习
1. Git的基础命令
1. Hexo框架
1. Hexo更换主题

用命令行敲命令是一种**Geek**行为，我觉得还挺有趣的。

   `Geek是指极客，通常被用于形容对计算机和网络技术有狂热兴趣并投入大量时间砖研的人。所以俗称发烧友或怪杰。`

有点意思，下面这张gif可以形容我的心情：

![](https://qgt-style.oss-cn-hangzhou.aliyuncs.com/newcoursep4/g1/g1-2-2/tenor.gif)


#### git add
git add是提交的第一步，我们一般使用下面的命令

```git add ```

git add .和上面的命令效果是一样的，本课程全部使用git add -A
A就是-all的意思

#### git commit

git commit 是提交的第二步，我们一般使用下面的命令：

```git commit -m "本次提交的修改的备注"```

```新创建的文件必须要按照顺序进行提交，如果只是修改文件，并没有创建文件，也可以使用git commit -am "本次提交的修改的备注" 来合并前面两个步骤。```

#### git push

git push 是提交的第三步,git push的情况相对比较复杂,分为以下几种情形

* 第1次提交到本分支 
* 第2-n次提交到本分支 
* 提交到其他分支

#### 第1次提交到本分支

第一次提交到本分支时时间比较长，命令为:

```git push origin master```

origin是远程仓库的默认名称,master是我们的分支名称(主分支)。

```绝大多数情况下我们一个工程只会绑定一个远程仓库，比如我们课程中的GitHub，但是Git是支持绑定
   多个远程仓库的，如果绑定了多个，比如同时绑定了GitHub和Gitee，那么此时origin要替换为相应的
   远程仓库名称。

    当你在其他分支提交时，master要替换为相应的分支名
```

#### 第2-n次提交到本分支 

从第二次提交到本分支，提交的命令可以简化为，

```git push```

#### 提交到其他分支

如果我们需要提交到b分支,那么我们可以输入这个命令

```git push orgin b```

#### git pull


