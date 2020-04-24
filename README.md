+ 先从github创建一个空的仓库
先从github创建一个空的仓库，并复制链接地址创建仓库

+ 初始化本地仓库，并提交内容到本地
需要先打开 命令行终端，然后通过 cd 命令切换到需要添加到github 的项目的目录下，然后依次执行如下命令， 具体命令及其含义如下：
    - touch README.md 创建说明文档，

    - git init 初始化本地仓库

    - git add . 添加全部已经修改的文件，准备commit 提交 该命令效果等同于 Git add -A

    - git commit -m ‘提交说明’
将修改后的文件提交到本地仓库，如：git commit -m ‘增加README.md说明文档’

+ 连接到远程仓库，并将代码同步到远程仓库
    - git remote add origin 远程仓库地址连接到远程仓库并为该仓库创建别名 , 别名为origin . 这个别名是自定义的，通常用origin ;远程仓库地址，就是你自己新建的那个仓库的地址，如：git remote add origin https://github.com/CnPeng/MyCustomAlertDialog.git 这段代码的含义是： 连接到github上https://github.com/CnPeng/MyCustomAlertDialog.git 这个仓库，并创建别名为origin . （之后push 或者pull 的时候就需要使用到这个 origin 别名）
    - git push -u origin master创建一个 upStream （上传流），并将本地代码通过这个 upStream 推送到 别名为 origin 的仓库中的 master 分支上-u ，就是创建 upStream 上传流，如果没有这个上传流就无法将代码推送到 github；同时，这个 upStream 只需要在初次推送代码的时候创建，以后就不用创建了另外，在初次 push 代码的时候，可能会因为网络等原因导致命令行终端上的内容一直没有变化，耐心等待一会就好。

    - 继续修改本地代码，然后提交并推送到github做完上面三个步骤之后，就实现了将本地代码同步到github的功能，接下来要做的事情就是继续修改代码，然后提交并推送到github
+ git add .
添加全部修改的代码，准备提交

+ git commit -m ‘提交说明’
将修改后的代码先提交到本地仓库

+ git pull origin master --allow-unrelated-histories
如果是多人协作开发的话，一定要先 pull ，将 github 的代码拉取到本地，这样在 merge 解决冲突的时候稍微简便些。默认拉取到 master分支（如果只是自己做这个项目，可以忽略pull）

+ git push origin master
将代码推送到 github , 默认推送到 别名为 origin 的仓库中的 master 分支上。

+ 注意事项：
如果有多个远程仓库 或者 多个分支， 并且需要将代码推送到指定仓库的指定分支上，那么在 pull 或者 push 的时候，就需要 按照下面的格式书写：git pull 仓库别名 仓库分支名
git push 仓库别名 仓库分支名
