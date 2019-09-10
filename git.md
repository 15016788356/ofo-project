 ## git   github
安装git
linux  sudo apt-get install git
windows  设置
git config --global user.name "Your Name"
git config --global user.email "email@CherryPeng.g@Gmail.com"

## 创建版本库 repository
mkdir  name
cd name
pwd 用于显示当前目录
git init 将目录变成Git可以管理的仓库(可以使用 ls -ah 查看隐藏的git文件夹)

将文件放入Git仓库
git add <file> (Unix哲学)
git commit 提交到仓库
git commit -m "this is my first txt"    -m <comment>

时光穿梭
git status 查看仓库状态
git diff <file> 查看修改

git log 显示最近到最远的提交日志 可查看3次 参数 --pretty=oneline

版本回退
git reset --hard HEAD^      (HEAD表示当前版本)
git reset --hard HEAD~100

git reset --head <1094a>(版本号 可不必写全)

git reflog 查看记录命令

git diff HEAD -- fileName 查看工作区和和版本库最新版本的区别

git checkout --file 丢弃工作区的修改

git reset HEAD <file> 把暂存区的修改回退到工作区

git rm fileName 删除文件 ---> git commit  git checkout --fileName 一键还原

## 创建SSH Key
ssh-keygen -t rsa -C "yourEmail"

git remote add origin git@github.com:michaelliao/learngit.git 推送仓库设置
git push -u origin master  git push 把当前master分支推送到远程 第一次推送加参数 -u

## 从远程库克隆
git clone git@github.com:michaelliao/gitskills.git

创建分支
git checkout -b dev   (-d 表示切换分支) git branch dev    git checkout dev
git branch 查看当前分区
git merge dev  合并指定分区到当前分区

git branch -d dev 删除分支
--no-ff参数，表示禁用Fast forward

先把工作现场git stash一下 再git stash pop，回到工作现场；
git cherry-pick <commit>命令，把bug提交的修改“复制”到当前分支
如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除。

git remote 查看远程库信息
git remote -v 详细信息
git rebase 把分叉的提交历史“整理”成一条直线

git tag v1.0 给分支打标签 git show <tagname>查看标签信息 
创建带有说明的标签，用-a指定标签名，-m指定说明文字
$ git tag -d v0.1 删除标签
git push origin <tagname> 推送某个标签到远程
git push origin --tags 一次性推送全部尚未推送到远程的本地标签
 git push origin :refs/tags/v0.9 删除远程标签,先删除本地标签

 git config --global color.ui true 让Git显示颜色