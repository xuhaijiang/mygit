11

# Git
### git 初始化
	git init

### 空库初始化(服务端)
	git init --bare mygit.git

### 查看配置信息
	git config --list

### git 添加远程库


> 如果你还没有克隆现有仓库，并欲将你的仓库连接到某个远程服务器，你可以使用如下命令

> 如此你就能够将你的改动推送到所添加的服务器上去了

	git remote add origin http://github.com/xuhaijiang

### 检出仓库
	git clone https://github.com/spring-projects/spring-boot.git

### git 状态
	git status

### git 添加文件
	git add readme.md

### git 提交文件
	git commit -m "本次提交说明"

### git 推送改动
	git push origin master

### git stage控件比较

> git diff source_branch target_branch

	git diff --staged

### git 回退
	git reset readne.md

### git 删除
	git rm "*.txt"

### 创建分支
	git branch master1

### 切换分支
	git checkout master1

### 删除分支
	git branch -d master1

### 分支合并

>合并其他分支到你的当前分支

	git merge master1

### git 提交到远程 [master](https://github.com/xuhaijiang/mygit.git) 分支
	git push origin master

### 更新你的本地仓库至最新

	git pull