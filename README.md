# GitTutorials
GitTutorials

# github的默认分支有master改为main

防止遗忘，特记录以下例子：
## 案例1:

1.克隆
git clone https://github.com/oysg/BookManagerSystem.git

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
git remote add origin https://github.com/oysg/BookManagerSystem.git

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
Username for 'https://github.com': 
Password for '':
To https://github.com/oysg/JapaneseMaterial.git
 ! [rejected]        main -> main (non-fast-forward)
 
 
error: failed to push some refs to 'https://github.com/oysg/JapaneseMaterial.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.


解决方案：

git pull --rebase origin main

git push origin main

案例 3
1. case

echo "# test" >> README.md

git init

git add README.md

git commit -m "first commit"

git branch -M main

git remote add origin https://github.com/oysg/test.git

git push -u origin main

2.case

…or push an existing repository from the command line

git remote add origin https://github.com/oysg/test.git

git branch -M main

git push -u origin main
