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
