## git pull

### git从远程pull
git init

git remote add origin git@github.com-qinzhu:614756773/huoguo.git
(git remote set-url origin 更改后的链接)

git branch -r 查看从远程pull到本地的有哪些分支

新建master分支（默认当前为master分支）

git pull origin master    pull远程master分支，默认将当前分支和远程master分支合并

再次查看git branch -r 和git branch

如果还想拉其他分支，需要pull

如，我还想pull远程的dev分支

不过在这之前，需要新建dev(或其他名字，最好和远程一样),再进入dev分支，再pull

git pull origin dev

再查看git branch -r 会发现多了一个origin/dev

同时远程dev和本地dev合并

如果要push的话，可以用

git push --set-upstream origin dev将本地分支和远程分支彻底关联起来

### git pull注意事项
git pull这个命令，我们经常会用，它默认是使用**merge**方式将远端别人的修改拉到本地；

如果带上上参数git pull -r，就会使用**rebase**的方式将远端修改拉到本地。

这二者最直观的区别就是：merge方式合并的分支会有很多「分叉」，而rebase方式合并的分支就是一条直线。

对于多人协作，merge方式并不好，多分支画面肯定杂乱，杂乱就意味着很容易出问题，所以一般来说，实际工作中更**推荐使用rebase**方式合并代码。

![](media/1.jpg)

我站在dev分支，使用git rebase master，把dev接到master分支之上。Git 是这么做的：

首先，找到这两条分支的最近公共祖先LCA，然后从master节点开始，重演LCA到dev几个commit的修改，如果这些修改和LCA到master的commit有冲突，就会提示你手动解决冲突，最后的结果就是把dev的分支完全接到master上面。
