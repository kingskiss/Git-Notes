
1. 配置git
git config --global user.name "kingskiss"
git config --global user.email "btxddwnj@hotmail.com"

2. 查看配置信息
git config --list
git config user.name

3. 如果希望在克隆的时候，自己定义要新建的项目目录名称，可以在上面的命令最后指定：
git clone git://github.com/schacon/grit.git mygrit

4. 检查当前文件状态
git status

5. 跟踪新文件
git add note.md

6. gitignore
```
*.a 	# 忽略所有.a结尾的文件
！lib.a 	# 但lib.a除外
/TODO	# 仅仅忽略项目跟目录下的TODO文件，不包括subdir/TODO
build/	#忽略build/目录下的所有文件
doc/*.txt # 会忽略doc/notes.txt 但不包括doc/server/arch.txt
```

7. 查看已暂存和为暂存的更新
要查看尚未暂存的文件更新了哪些部分，不加参数直接输入
git diff
此命令比较的是工作目录中当前文件和暂存区域快照之间的差异，
也就算修改之后还没有暂存起来的变化内容。
若要看已经暂存起来的文件和上次提交时的快照之间的差异，可以用
git --staged

8. 提交更新
git commit -m "created or modified some files"
跳过使用暂存区域直接提交
git commit -a -m "xxx"

9. 移除文件
git rm
如果删除之前修改过并且已经放到暂存区域的话，则必须要用强制删除选项-f，
以防误删除文件 后丢失修改的内容。
另外一种情况是，我们想把文件从git仓库中删除，但仍然希望保留在当前工作目录中。
git rm --cached readme.txt

git rm log/\*.log	此命令删除所有log/目录下扩展名为.log的文件。
git rm \*~		此命令会递归删除当前目录及其子目录中所有~结尾的文件。

10. 移动文件
git mv readme.md readme
相当于运行了下面三条命令：
mv readme.md readme
git rm readme.md
git add readme

11. 查看提交历史
git log
我们常用-p 选项展开显示每次提交的内容差异，用-2则仅显示最近的两次更新
git log -p -2

显示简要的增改行数统计:
git log --stat

--pretty选项
git log --pretty=oneline
git log --pretty=format:"%h - %an, %ar :％s"

常用的占位符写法及其代表的意义。
%H 		提交对象(commit)的完整哈希字串
%h 		提交对象的简短哈希字串
%T 		树(tree)对象的完整哈希字串
%t 		树对象的简短哈希字串
%P 		父对象(parent)的完整哈希字串
%p 		父对象的简短哈希字串
%an 		作者(author)的名字
%ae 		作者的email地址
%ad 		作者修订日期(可以用 -date= 选项定制格式)
%ar 		作者修订日期，按多久以前的方式显示
%cn 		提交者(committer)的名字
%ce 		提交者的email
%cd 		提交日期
%cr 		提交日期，按多久以前的方式显示
%s 		提交说明

--graph选项
git log --pretty=format:"%h %s" --graph

git log命令支持的常用选项
选项 					说明
-p 			按补丁格式显示每个更新之间的差异
--stat 			显示每次更新的文件修改统计信息
--shortstat 		只显示--stat中最后的行数修改添加移除统计
--name-only 		仅在提交信息后显示已修改的文件清单
--name-status 		显示新增、修改、删除的文件清单
--abbrev-commit 	仅显示SHA-1的前几个字符，而非所有的40个字符
--relative-date 		仅用较短的相对时间显示(比如， “2 weeks ago)
--graph  		显示ASCII图形表示的分支合并历史
--pretty 		使用其他格式显示历史提交信息。可用的选项包括：
			oneline,short,full,fuller和format(后跟指定格式)

限制输出长度
列出所有最近两周内的提交：
git log --since=2.weeks
可用给出各种事件格式，比如具体的某一天("2010-10-10")，
或者是从多久以前("2 yeas 1 day 3 minutes ago")
选项 			说明
-(n) 		仅显示最近的n条提交
--since, --after  仅显示指定时间之后的提交
--until, --before 仅显示指定事件之前的提交
--author 	仅显示指定作者相关提交
--committer 	仅显示指定提交者相关的提交

使用图形化工具查阅提交历史
gtik

12. 撤销操作

修改最后一次提交
git commit --amend

取消已经暂存的文件
git reset HEAD <file>...

取消对文件的修改
git checkout --<file>...

13. 远程仓库的使用
查看当前的远程库
git remote
git remote -v 		显示对应的clone地址

添加远程仓库
git remote add [shortname] [url]
git remote add pd git@github.com:paulboone/ticgit.git

比如说，要抓取所有Paul有的，但本地仓库没有的信息，可以运行
git fetch pd

从远程仓库抓取数据
git fetch [remote-name]
此命令会到远程仓库中拉取所有你本地仓库中还没有的数据



