# Git
### git 初始化
`git init` 

### 空库初始化(服务端)
`git init --bare mygit.git`

### 查看配置信息
`git config --list`

### git 添加远程库
`git remote add origin http://github.com/xuhaijiang`

### git 状态
`git status`

### git 添加文件
`git add readme.md`

### git 提交文件
`git commit -m "本次提交说明"`

### git stage控件比较
`git diff --staged`

### git 回退
`git reset readne.md`

### git 删除
`git rm "*.txt"`

###创建分支
`git branch master1`

###转换分支
`git checkout master1`

###删除分支
`git branch -d master1`

###分支合并
`git merge master1`

### git 提交到远程 [master](https://github.com/xuhaijiang/mygit.git) 分支
`git push origin master`
