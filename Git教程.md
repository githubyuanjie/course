# Git是什么？
> 也许你听过[*github*](https://github.com/),但是或许你没有听过**Git**。

但是，**Git和Github是两个完全不同的东西**，GitHub是对Git的仓库进行托管。
在说什么是Git之前，我们先说些别的。
## 版本控制
**版本控制**是我们生活中必不可少的，它可以用于回溯进程，重温经典，修改bug等等。
而我相信大多数人常用的**版本控制系统**（*Version Control System*）都是**压缩文件**。
1. 将自己想要控制的版本文件压缩
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305102304520.png)
2. 等到有需求时，把此版本解压出来进行修改
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305102306341.png)

3. 修改版本再压缩
以上绝大多数人的版本控制方法。
### 常见方法优点
* 简单
* 方便
* 机械
### 常见方法缺点
* 不适合多人
* 不适合异地
* 容易丢失
* 耗费内存
* 不专业

---
> 综上原因，Git便横空而出了

毫无疑问的，GIt是一个专业的**版本控制系统**（**VCS**），它能解决以上所有问题，也继承了解压式版本控制的所有优点，**草履虫也能轻松掌握**。
# 如何使用Git？
## Git的下载和安装
* 首先进入[*GIt官网*](https://git-scm.com/)
* 点击Downloads![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305102318371.png)
* 对照操作系统选择下载版本![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305102319052.png)
* 选择操作系统位数（一般为64位）![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305102322149.png)
* 下载完成后点击文件开始安装
* 接下来**一路回车法**（*一直下一步*）即可。当然也可以自己修改一下安装目录。
* 如果正确安装了Git，右键鼠标可以看到两个Git版本![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305122228878.png)

## ==Git的原理及工作流程（非常重要）==
### 工作区
Git*本地*有**三个工作区域**
* 工作目录（Working Directory）
* 暂存区（Stage/index）
* 资源库（Repository或者Git Directory）
如果再加上远程的Git仓库（Remote Directory）就一共**四个工作区**。
其**转化关系**如下图![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305102347994.png)
说的通俗一点：
* 
```
git add
```
用于将文件进入*修改模式*（保存差异）
* 
```
git commit
```
用于提交对比差异
* 
```
git push
```

用于将修改版本发送到到远程仓库
### 工作流程
一般来讲Git的工作流程主要分为三步
1. 在工作目录中创建或修改文件
2. 将需要保存的修改文件提交到暂存区
3. 将暂存区域的文件提交到git仓库

因此Git中文件的状态对应有三种
1. 已修改（modified）
2. 已暂存（staged）
3. 已提交（committed）

## Git的食用指南
在正式开始学习之前，请把文件管理器中的**文件扩展名**和**隐藏的项目**打开!，这是作为开发者所必须的.![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305122234588.png)

### Git模式选择
如果你正确安装了Git，你可以在开始菜单中看到3个Git版本
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305112307872.png)
先来说说这3个版本的特点
* Git Bash：最常用,最推荐,是Unix和Linux风格的命令行
* Git CMD：Winowdows风格命令行
* Git GUI：图形界面,不建议初学者使用,类似Scartch（？

以下教程围绕Git Bash展开

### 基本Linux命令
由于Git Bash是Linux风格的命令行，所以我**建议**先学一些基础的Linux命令（选修

>ps:如果命令太小看不清，可以用Ctrl＋鼠标滚轮调整字体大小

1. cd: 改变目录
2. cd ..: 返回上级目录
3. pwd: 显示当前目录路径
4. ls(||): 列出当前目录所有文件，如果加上(||)会更加详细
5. touch: 新建一个文件，例如
```
touch C_is_the_best_language.py
```
意思为在当前目录创建文件“C_is_the_best_language.py”
6. rm: 删除一个文件
7. mkdir: 新建一个文件夹
8. rm -r: 删除一个文件夹
9. mv: 移动文件，例如
```
mv C_is_the_best_language.py src
```
其中“C_is_the_best_language.py”为要移动的文件，“src”为要移动到的目标文件夹
10. reset: 初始化终端
11. clear: 清屏
12. history: 历史指令
13. help: 帮助
14. exit: 退出
15. "#" : 加注释

> 千万不要随意使用~~~"rm -rf"~~~,此代码意为删除根目录下所有文件,不要轻信他人无聊的寻乐,大多只是居心叵测的小丑罢了.

如果你有打算认真学习开发，以上内容对你而言是**基础中的基础**，请**务必掌握，务必自己实操几次**

### Git的基本配置
查询Git所有配置：
```
git config -l
```
查询Git所有系统配置
```
git config --system --list
```
查询Git用户自配的配置
```
git config --global --list
```
#### 设置Git用户名以及邮箱（必要）
Git的用户名和邮箱只是一个本地读写文件而已，随时可以修改，请放心配置.
在Git Bash中（右键打开），输入以下指令，记得分开复制并且修改数据
```
git config --global user.name "yuanjie（自行修改）"
git config --global user.email 104556222@qq.com(自行修改)
```
如果你使用了"--global"则是**全局配置**，只用配置一次。如果去掉"--global"，则是**临时配置**，下次使用需要重新配置。
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305112343243.png)
#### Git的配置文件
前面我们说过，Git的配置实质上是一个读写文件，全局（global）和系统（system）配置是分开放的
* 系统：
安装目录的etc文件夹下的gitconfig文件，例如
‪F:|Git|etc|gitconfig
* 全局：
系统盘用户目录的.gitconfig文件，例如
C:|Users|JSxhq|.gitconfig
这个这个文件是**可以直接进行编写**的.
*以上文件都可以用记事本直接打开*

>不仅Git，许多软件的配置都是一个读写文件，所以可以通过代码来改写其中内容，达到修改配置的目的！

### 搭建Git项目（核心）

#### 常用指令与创建工作目录
Git帮助你管理的文件夹叫做Git的工作目录（WorkSpace），最好不要有中文.

常用的命令一共只有6个，要求牢记，其用法和具体命令如下图：
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305122215182.png)
##### 本地仓库搭建
创建本地仓库的方法有二：
1. 创建全新仓库
2. 克隆远程仓库

###### 创建全新仓库
1. 首先，我们在任意磁盘创建Git的工作目录，例如*E:|gitwork*
2. 在工作目录右键打开Git Bash![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305122230683.png)
3. 在终端中输入
```
git init
```
以初始化工作目录![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305122238228.png)
请检查回车后，工作目录中是否多了一个隐藏的“.git”文件夹。

###### 克隆远程仓库
1. 首先，我们在任意磁盘创建Git的工作目录，例如*E:|gitwork*
2. 在工作目录右键打开Git Bash![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305122230683.png)
3. 在码云或者Github上找到你要克隆的仓库,如果没有账号的话可以先注册，迟早会用上,[注册教程](https://www.yuanjieknowledge.cn/index.php/2023/05/09/photo_house/)
4. 以Github为例（国内进不去就用[**码云**](https://gitee.com/)，原理完全相同）,找到你要克隆的仓库,例如[*这篇教程*](https://github.com/githubyuanjie/course),到仓库界面后，点击"<>code",随意选择一个镜像链接，点击*双矩形*复制![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305122347448.png)


5. 在终端中输入：
```
# 把"[url]"改成远程仓库的链接
git clone [url]
```
例如：
```
git clone https://github.com/githubyuanjie/course.git
```
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305122349017.png)
克隆完成后可以看到**对应的文件名**出现在工作目录.

#### 配置SSH公钥

##### 什么是SSH公钥？
简单来说，SSH公钥就像是一个人的指纹，它是独一无二的，用于安全地**验证和授权**远程SSH（Secure Shell）客户端访问远程服务器或计算机系统.
配置了SSH公钥之后，我们就可以做到免密码登录等等。

##### 获取Github的SSH公钥
1. 在任意目录打开Git，输入：
```
ssh-keygen -t rsa
```
然后**一路回车**,切记不要输入任何信息!
2. 进入系统盘的用户文件夹中的.ssh文件夹，例如C:|Users|JSxhq|.ssh.查看是否生成了两个文件
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305130044198.png)
3. 进入Github设置公钥界面
4. 点击“New SSH key”
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305130032247.png)
5. 将.ssh中带.pub后缀的文件用记事本打开，并复制所有内容。
6. 粘贴复制内容到"Key”，“title”处填写最后一个等号后面的标识符。如JSxhq@DESKTOP-HA490KS.
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305130051730.png)
7. 确认无误后点击“Add SSH key”

那么SSH key就配置好了!

#### 创建自己的Github仓库
1. 进入[Github主页](https://github.com/),点击左上角“New”![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305130115069.png)

2. 在“Repository name”中输入自己的仓库名字（随意），例如：git_learn
3. 在“Description”中输入对自己这个仓库的介绍，例如：This is my learning of git
4. 点击”Create repository“以创建仓库![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202305130122537.png)

其他的几个地方都十分简单可以自行研究一下Github，多创建几个仓库试试，把每个选项的功能弄明白。

### Git与Pycharm联调（全网独家，最详细）