## Study Git [更多资料请看 Git-Book](https://git-scm.com/book/zh/v2/)

第一步：获取 git 仓库，有以下两种方式

##在现有目录总初始化仓库

```bash
$ git init
```

##克隆现有的仓库

```bash
$ git clone git@github.com:wanglq80/studygit.git
```

第二步：检查当前文件状态

```bash
$ git status
```

第三步：跟踪新文件或暂存已修改文件，该命令使用文件或目录的路径作为参数

```bash
$ git add <file or path>
```

第四步：添加忽略文件，文件名为.gitignore，列出要忽略的文件模式

```bash
$ touch .gitignore
```

第五步：提交更新，每次提交前，先用git status看下，要提交的文件是否都已经暂存起来

```bash
$ git status
$ git commit -m 'some message'
```

如果希望每次提交时，跳过使用暂存区域，可以使用以下命令（此方式下Git会自动把所有已经跟踪过的文件暂存起来一并提交，从而跳过 git add 步骤）

```bash
$ git commit -a -m 'some message'
```

第六步：查看提交历史

```bash
$ git log
```

git log常用参数：

```bash
$ git log -p -2
```

选项-p，用来显示每次提交的内容差异。
选项-2，用来显示最近两次提交。
选项--stat，用来显示每次提交的简略的统计数据。
选项--since="2017-10-17"，用来显示指定日期之后的提交。（或使用 --after）
选项--befor="2017-10-19"，用来显示指定日期之前的提交。（或使用 --until）
选项--author,用来显示指定作者相关的提交。
选项--committer，用来显示指定提交者相关的提交。

第七步：撤销操作

有时候我们提交完了才发现漏掉了几个文件没有添加，或者提交信息写错了。 此时，可以运行带有 --amend 选项的提交命令尝试重新提交：

```bash
$ git commit --amend
```

取消暂存的文件:

```bash
$ git reset HEAD <file>
```

撤销对文件的修改：

```bash
$ git checkout --<file>
```

第八步：远程仓库的使用

查看远程仓库：

```bash
$ git remote
```

可以指定选项 -v，用来显示需要读写远程仓库使用的 Git 保存的简写与其对应的 URL。

```bash
$ git remote -v
```


添加远程仓库：

```bash
$ git remote add <shortname> <url>
```

从远程仓库中抓取与拉取：

```bash
$ git fetch [remote-name]
```

必须注意 git fetch 命令会将数据拉取到你的本地仓库 - 它并不会自动合并或修改你当前的工作.当准备好时你必须手动将其合并入你的工作。

运行 git pull 通常会从最初克隆的服务器上抓取数据并自动尝试合并到当前所在的分支。

```bash
$ git pull
```

推送到远程仓库：

```bash
$ git push [remote-name] [branch-name]
```

远程仓库重命名：

```bash
$ git remote rename newrepo study-git
```
以上命令，将newrepo重命名为study-git

移除远程仓库：

```bash
$ git remote rm newrepo
```
以上命令，将删除远程仓库 newrepo

第九步：打标签

附注标签：

```bash
$ git tag -a v1.4 -m 'my version 1.4'
```

轻量标签：

```bash
$ git tag v1.4-lw
```

后期打标签：

```bash
$ git tag -a v1.2 <提交的校验和>
```

共享标签：

```bash
$ git push [remote-name] [tagname]
```

查看标签信息：

```bash
$ git show [tagname]
```

通过使用 git show 命令可以看到标签信息与对应的提交信息

第十步：分支管理

创建分支：

```bash
$ git branch [branch-name]
```

分支切换：

```bash
$ git checkout [branch-name]
```


