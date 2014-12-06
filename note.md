
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