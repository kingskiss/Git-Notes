
# 1. 配置git
git config --global user.name "kingskiss"
git config --global user.email "btxddwnj@hotmail.com"

# 2. 查看配置信息
git config --list
git config user.name

# 3. 如果希望在克隆的时候，自己定义要新建的项目目录名称，可以在上面的命令最后指定：
git clone git://github.com/schacon/grit.git mygrit

# 4. 检查当前文件状态
git status

# 5. 跟踪新文件
git add note.md