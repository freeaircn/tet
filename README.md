hello git!

version 1.0 done

f1 branch {
    part 1
}

f2 branch {
    part 1
}

PC2 f2 branch {
    part 1
}

【使用】
1 PC1新建仓库

2 PC1关联remote，用cmd

3 PC1本地master提交版本，push至remote master

4 PC1本地创建分支 f1，PC1本地提交分支f1，并push分支f1至remote

5 PC1本地合并分支f1，用cmd

6 PC1本地删除分支f1，用cmd，remote侧分支无变化

7 PC1发起remote删除分支f1


8 PC2 拉取remote 所有分支，含master，其他分支
  1 PC2创建仓库，用cmd
  2 PC2创建本地分支（分支名对应远程分支），并建立本地分支与远程分支的关联。git创建仓库时，默认有了master分支。
    # 关联目的是如果在本地分支下操作： git pull, git push ，不需要指定在命令行指定远程的分支
    1 本地拉取remote master分支
      git pull origin master
    2 本地master 关联remote master分支
      git branch --set-upstream-to=origin/master
    3 本地创建f2分支，并拉取remote f2分支
      git switch -c f2
      git pull origin f2
    4 本地f2 关联remote f2分支
      git branch --set-upstream-to=origin/f2
    
9 PC2 在f2分支上修改，本地提交，推送至remote

10. PC2 将f2分支合并至master分支，本地提交，推送至remote
    git merge --no-ff -m "merge from f2 branch" f2
    git push origin


两条线：
master
dev


1 基于master 创建dev分支
2 本地pull remote/dev分支进行修改，本地push 至remote/dev
3 本地修改dev完毕，本地合并dev分支至master，再push至remote/master

2023-5-18

2023-5-18 dev 分支1

dev PC1 - 分支2