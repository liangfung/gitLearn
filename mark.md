使用git，要先弄明白什么是暂存区（stage）

命令                               |  作用
---------------------------       | ---------------------------
git checkout -- \<File\>          | 将版本库的版本**替换**工作区的版本<br>（可撤销工作区修改，反正就是**还原工作区**至版本库或者暂存区）
git reset HEAD \<File\>           | 撤销暂存区(unstage) 
git reset commit_id               | 版本回退，但**不会撤销工作区**的修改
git reset ***--hard*** commit_id  | 版本回退并**撤销工作区**修改
git diff                          | 比较work dict和stage
git diff --cached                 | 比较stage和branch
git checkout \<branch\>           | 切换分支

- 关于git checkout -- \<File\>
    这操作是还原工作区的修改，有两种情况
    1. 工作区修改了，还没有放到暂存区(stage)，这时用git checkout --\<File\>的话，会撤销工作区修改至git commit状态(当前分支版本)
    2. 工作区修改了，也加入到暂存区了，之后又修改了，这时用git checkout -- \<File\>,会还原修改至暂存区

小结
- 只有**git checkout -- \<File\>** 和 **--hrad**会动工作区的修改
- git add 是放到暂存库，git commit之后才会到版本库
