
#### 初始化仓库


##### 创建本地仓库
```
git init 
```


##### 拉取远程仓库

*SSH*
```
git clone git@github.com:用户名/仓库名.git  #配置了SSH密钥后可以使用，需要关VPN
```

HTTPS
```
git clone https://github.com/用户名/仓库名.git    #不稳定，可能连不上
```




#### 工作流程

工作区——暂存区——提交(分支)是保存的三个层级，可逐级保存/撤销。

##### 暂存
```
git add  <file/folder>  #提交修改到暂存区
git add  .     #提交当前目录所有修改到暂存区

git rm <file>    #删除文件，并将此操作视作"一次修改"提交到暂存区
git rm -r <folder> #删除文件夹

git mv <old> <new> #移动或重命名文件/夹，并将此操作视作"一次修改"提交到暂存区
```

##### 提交
```
git commit -m  '说明信息'     # 提交暂存区修改给仓库
git commit --amend -m 'xxx'  # 合并上一次提交（用于反复修改，避免多条冗余记录）
git commit -am 'xxx'         # 将add和commit合为一步
```

##### 撤销
```
git restore file     # 撤销工作区改动。回到暂存区的版本，
                       如果暂存区没有，则回到上次commit的版本 

git reset --soft        # 撤销上次提交，但不撤销暂存区
git reset --mixed       # 撤销上次提交，暂存区也是
git reset --hard        # 撤销上次提交，暂存，连带工作区回到上上个提交状态
```


#### 管理分支


##### 创建，删除，切换
```
git branch        # 列出本地分支（*标注的是现在位于的分支）

git branch 分支   # 创建新分支

git branch -d 分支   # 删除分支

git branch -m <新分支名> #分支改名
```

```
git checkout 分支
git switch 分支     # 切换到某个分支
```

```
git checkout -b 分支   #创建并切换到新分支
```

##### 合并
```
git merge 分支     # 将当前分支与指定分支合并，产生新提交(新节点)

#合并规则:
   对比两分支与其共同的父节点。两分支不相交的的修改会被各自采纳；
   相交的修改会生成待解决冲突文本：

<<<<<<< HEAD
当前分支的内容
=======
被合并分支的内容
>>>>>>> feature
```

```
git rebase 分支  #将当前分支接到另一个分支末端

#拼接规则：
     父节点之后，当前分支的每次新提交逐一应用到目标分支的最新提交；
     进行多次合并判断，合并规则同merge，
     
     某次合并因冲突而终止时，手动解决后用
     git add <file>  将解决了冲突的文件传到暂存区；
     git rebase --continue 继续下次提交与合并

     
```

##### 全息储存

工作区，暂存区都是所有分支通用。意味着
从A分支切换到B分支时，工作区，暂存区都没变。但一般来说，你需要的是：
* 工作区进入B分支的最新状态
* 保存A分支的工作区，暂存区内容
因此**切记**切换前要保存
```
git stash  #保存当前分支工作区，暂存区内容，下次切换时复原
```


#### 远程协作


##### 关联远程仓库
```
git remote add origin <HTTPS或SSH>   
#origin是本地使用的远程仓库别名，避免每次写完整HTTPS或SSH

git remote -v       #查看远程仓库地址（HTTPS或SSH）

git remote remove origin #删除一个远程关联名，一般一个仓库就关联一个origin，换绑远程请先删除原来的关联，否则origin是被占用的
```

##### 远程跟踪分支

 远程跟踪分支与同名远程分支强绑定。位于本地，是由fetch从远程拉取的镜像。
```
git fetch origin   #从远程获取最新提交,作为独立的远程跟踪分支存在，名字是origin/分支

git merge origin/分支     #可以自行判断并决定要不要与本地分支merge

git merge  #当前分支已经有upstream了，则省略输入upstream
```

远程跟踪分支可以作为本地分支的upstream，
```
git branch --set-upstream-to=origin/远程分支名   #为当前分支指定upstream
```

指定upstream,意味着需要分支作为参数的地方，不输入都默认以upstream作为参数。对于与远程分支同步的本地分支，同步操作很方便：

##### 推送&拉取
```
git push origin feature  #本地分支推送远程分支
git pull origin feature  # 拉取远程分支到本地，等同于 fetch + merge

git pull   #指定了stream后，简写
git push   #指定了stream后，简写
```

```
git push --set-upstream origin feature  #首次推送，推送同时建立远程跟踪并指定为upstream
```

```
git push origin <分支名> --force   #强制覆盖性推送远程，新手常用
```

##### git clone 的支线分支

git clone 默认在本地创建main 或 master  分支，此外所有分支创建为远程跟踪分支。
本地创建main 或 master  分支，自动设置了其upstream，因此在主分支下可以直接
```
git push
git pull
```

想要本地同步更新main以外的分支，可以这样，
```
git checkout -b feature origin/feature 

# 创建并切换到本地分支feature，创建内容用origin/feature，且会自动建立upstream
```




#### 状态查询

##### 查看提交历史
```
git log              #完整历史 

git log --oneline --graph   #简洁图形化展示
```


##### 查看未保存改动

目录文件右边有状态提示:(文件级)
M  （Modified，已修改）
R     (Renamed，已重命名/移动）
U     (Untracked,未被跟踪，没被add过)
U   （Unmerged，合并冲突）？

此外文件内部，行级状态：
```
git diff               #未暂存的改动（会显示在行前，蓝）
git diff --staged      #查看已暂存但未提交的改动（会显示在行前，绿）
```

#### 配置SSH密钥

**windows**


##### 生成密钥

任意位置右键，打开Git Bash 终端
```
          #查看现有密钥，如果没有则创建
```

```
ssh-keygen -t ed25519 -C "your_email@example.com"   #生成密钥
#接下来回应提示。
 设置password:  回车不设置
 重复password:  同上

# id_ed25519 私钥
  id_ed25519.pub 公钥
```

##### 启用agent

不同终端要各自启用ssh-agent，方式不同

**Git Bash/linux 终端**
```
eval "$(ssh-agent -s)"        # 启动 ssh-agent
# 应显示：Agent pid 12345

ssh-add ~/.ssh/id_ed25519     # 将私钥添加到 ssh-agent
# 如果设置了密码，此时会提示输入
```


**powershell**

这个比较常用，尤其是作为vscode通用的终端
```
step1. 系统搜索栏查找powershell，管理员模式打开

step2. 启用agent服务:

Get-Service ssh-agent | Set-Service -StartupType Manual
Start-Service ssh-agent


step.3 修改私钥权限:
右键私钥 → 属性 → 安全 → 高级 → 禁用继承 → 从此对象中删除所有继承的权限；
添加 → 选择主体 → 查找自己用的用户添加权限。只勾选- 读取/读取和执行。

step4. 添加私钥到agent：

ssh-add C:\Users\用户名\.ssh\id_ed25519    
   
```


**验证连接**
```
ssh -T git@github.com 

#显示类似下面的消息就对了
Hi ttt125145! You've successfully authenticated, but GitHub does not provide shell access.
```

##### 在github添加
密钥文件夹.ssh在C盘用户根目录。

* 复制公钥内容，

* 去github settings——左边栏Access下的SSH and GPG keys —— New SSH key，

* 用公钥内容创建，名字随意。





#### 本地git用户
```
配置用户信息————一台电脑上只用配置一次(— gobal 全局)

git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```