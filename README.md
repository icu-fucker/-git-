快速指南
安装 Git
不讲，不会做退学
clone 代码
执行如下命令以创建一个本地仓库的克隆版本： git clone /path/to/repository

如果是远端服务器上的仓库，你的命令会是这个样子： git clone username@host:/path/to/repository （通过 SSH） 或者： git clone https:/path/to/repository.git （通过 https）

比如说 git clone https://github.com/geeeeeeeeek/git-recipes.git 可以将 git 教程 clone 到你指定的目录。

创建新仓库
创建新文件夹，打开，然后执行 git init 以创建新的 git 仓库。
可看可不看

/** 下面每一步中，你都可以通过 git status 来查看你的 git 仓库状态。(基本不需要) **/

工作流
可看可不看

/** 你的本地仓库由 git 维护的三棵“树”组成。第一个是你的 工作目录，它持有实际文件；第二个是 缓存区（Index），它像个缓存区域，临时保存你的改动；最后是 HEAD，指向你最近一次提交后的结果。 事实上，第三个阶段是 commit history 的图。HEAD 一般是指向最新一次 commit 的引用。现在暂时不必究其细节。 **/

添加与提交
你可以计划改动（把它们添加到缓存区），使用如下命令：

git add < filename >
git add *
这是 git 基本工作流程的第一步。使用如下命令以实际提交改动：

git commit -m "代码提交信息"
现在，你的改动已经提交到了 HEAD，但是还没到你的远端仓库。

推送改动
如果你还没有 git 仓库，可以在 GitHub 等代码托管平台上创建一个空（不要自动生成 README.md）的 repository，然后将代码 push 到远端仓库。

如果你还没有克隆现有仓库，并欲将你的仓库连接到某个远程服务器，你可以使用如下命令添加：

git remote add origin
如此你就能够将你的改动推送到所添加的服务器上去了。

这里 origin 是 < server > 的别名，取什么名字都可以，你也可以在 push 时将 < server > 替换为 origin。但为了以后 push 方便，我们第一次一般都会先 remote add。

你的改动现在已经在本地仓库的 HEAD 中了。执行如下命令以将这些改动提交到远端仓库：

git push origin master
可以把 master 换成你想要推送的任何分支。
