# GitTutorials
GitTutorials

# github的默认分支有master改为main

防止遗忘，特记录以下例子：
## 案例1:

1.克隆
git clone https://github.com/ouyangshaogong/BookManagerSystem.git

2.添加文件
git add 1.txt

3.提交
git commit -m "1.txt"

4.push文件
git push origin main

## 案例2

1.本地创建目录并进入目录

mkdir githubTest

cd githubTest

2.初始化
git init

2.5 切换到main分支
 git checkout -b main

3.添加内容
git add 1.txt

4.将文件提交到暂时区
git commit -m "1.txt"

5.将本地仓库连接到远端仓库
git remote add origin https://github.com/ouyangshaogong/BookManagerSystem.git

6.将文件push到远端仓库
git push origin main

问题：

如果执行git remote add origin https://github.com/Flowerowl/stumansys.git，出现错误：fatal: remote origin already exists 

则执行以下语句：git remote rm origin.

再往后执行git remote add origin https://github.com/Flowerowl/stumansys.git 即可

问题：

在执行git push origin main时，报错：　error:failed to push som refs to

则执行以下语句：git pull origin main

先把远程服务器github上面的文件拉先来，再push 上去。

问题： 写完代码后，我们一般这样

git add . //添加所有文件

git commit -m "本功能全部完成"

执行完commit后，想撤回commit，怎么办？

回答：

HEAD^的意思是上一个版本，也可以写成HEAD~1

如果你进行了2次commit，想都撤回，可以使用HEAD~2

至于这几个参数： --mixed

意思是：不删除工作空间改动代码，撤销commit，并且撤销git add . 操作
这个为默认参数,git reset --mixed HEAD^ 和 git reset HEAD^ 效果是一样的。

--soft
不删除工作空间改动代码，撤销commit，不撤销git add .

--hard
删除工作空间改动代码，撤销commit，撤销git add .

注意完成这个操作后，就恢复到了上一次的commit状态。

顺便说一下，如果commit注释写错了，只是想改一下注释，只需要：

git commit --amend

此时会进入默认vim编辑器，修改注释完毕后保存就好了。


问题:

$ git push origin main 报以下错

Logon failed, use ctrl+c to cancel basic credential prompt.
Username for 'https://github.com': 527722032zfl@gmail.com
Password for 'https://527722032zfl@gmail.com@github.com':
To https://github.com/ouyangshaogong/JapaneseMaterial.git
 ! [rejected]        main -> main (non-fast-forward)
 
 
error: failed to push some refs to 'https://github.com/ouyangshaogong/JapaneseMaterial.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.


解决方案：

git pull --rebase origin main

git push origin main



git lfs 常用命令

git lfs help // 查看git lfs的帮助

git lfs version  // 查看git lfs的版本号

git lfs track // 查看git lfs的文件追踪信息

git lfs track '*.dll' // dll文件用lfs来管理，会在根目录的.gitattributes文件中添加：*.dll filter=lfs diff=lfs merge=lfs -text

git lfs track "*.a" "*.dylib" "*.so" "*.lib" "*.dll"  // a、dylib、so、lib、dll文件用lfs来管理，会在根目录的.gitattributes文件中添加

*.dylib filter=lfs diff=lfs merge=lfs -text

*.so filter=lfs diff=lfs merge=lfs -text

*.lib filter=lfs diff=lfs merge=lfs -text

*.dll filter=lfs diff=lfs merge=lfs -text

*.a filter=lfs diff=lfs merge=lfs -text

git lfs track 'Guid.upk' // Guid.upk文件用lfs来管理，会在根目录的.gitattributes文件中添加：Guid.upk filter=lfs diff=lfs merge=lfs -text

git lfs track 'maps/*' // 根目录下maps文件夹中的所有文件用lfs来管理，会在根目录的.gitattributes文件中添加：maps/* filter=lfs diff=lfs merge=lfs -text

git lfs untrack 'Guid.upk' // Guid.upk文件不再使用lfs来管理

git lfs status  // 查看当前git lfs对象的状态

git lfs ls-files  // 查看当前哪些文件是使用lfs管理的

git lfs clone https://github.com/kekec/Test.git // 克隆包含Git LFS的远程仓库到本地

git lfs env  // 查看环境信息
