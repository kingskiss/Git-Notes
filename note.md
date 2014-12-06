
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