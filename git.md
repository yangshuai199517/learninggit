+ 改变file之后，使用git checkout - - file 使file回到最近的commit的状态

+ 改变file ，使用 git reset HEAD，就将add的作用去掉了，即unstaged changes ,就是说把改变从版本库中的暂存区从退出了，然后对file做的改变任然是保留的，如果要消除这个改变，使用git checkout - - file 即可。这儿需要指出的是如果使用的是git reset --hard HEAD的话，file将直接从git add之后的效果回复到最近一次commit的效果，就等同于git reset HEAD+git checkout - - file的效果。

+ 对于已经git add + git commit的版本，我们要回去上一次，就使用git reset —hard HEAD^就可以，这个时候git log就会把最近的一次commit的信息抹去，但是可以通过git reflog 来查找抹去的这一个版本号，然后如果要回到刚被抹去这一个版本，就先用git log 或者 git reflog去查版本号，然后，用git reset —hard (版本号)即可。

+ 如果要丢弃一个没有被合并过的分支，可以通过`git branch -D file强行删除。可以用git branch -d file

+ 从本地忘远程仓库推送，git push origin destination_place ，不管你在本地的哪个分支，都可以进行这个动作，就将本地的destination_place对应的版本推到远程仓库。

+ 多人协作的工作模式通常是这样：

  1. 首先，可以试图用`git push origin <branch-name>`推送自己的修改；
  2. 如果推送失败，则因为远程分支比你的本地更新，需要先用`git pull`试图合并；
  3. 如果合并有冲突，则解决冲突，并在本地提交；
  4. 没有冲突或者解决掉冲突后，再用`git push origin <branch-name>`推送就能成功！

  如果`git pull`提示`no tracking information`，则说明本地分支和远程分支的链接关系没有创建，用命令`git branch --set-upstream-to=origin/<branch-name> <branch-name> `。

+ 当git clone之后，你在这个版本里只有master分支，但是在远程仓库中还有其他分支，你为了能把那部分弄下来，需要使用在本地创建和远程分支对应的分支，使用`git checkout -b branch-name origin/branch-name`，本地和远程分支的名称最好一致，这样就可以了，第一个branch-name就是你在本地建的分支，而第二个是远程仓库的分支。

+ rebase操作可以把本地未push的分叉提交历史整理成直线；

+ 忽略某些文件时，需要编写`.gitignore`；

+ `.gitignore`文件本身要放到版本库里，并且可以对`.gitignore`做版本管理！

+ git还可以配置命令的别名，以及修改.git中的配置文件来达到配置的目的。

  ### 问题

+ diff文件是个什么鬼，怎么去用

+ lhadmin@10.231.133.115 

+ pw:0584822a#Qwe1

