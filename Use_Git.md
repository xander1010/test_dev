# 配置SSH Key
## 一、设置git的user name和email
* 如果你是第一次使用，或者还没有配置过的话需要操作一下命令，自行替换相应字段。

>1. git config --global user.name "xander"
>2. git config --global user.email  "xander1010@163.com"

* 说明：git config --list 查看当前Git环境所有配置，还可以配置一些命令别名之类的。
  
## 二、检查是否存在SSH Key
>1. cd ~/.ssh
>2. ls
>3. 或者
>4. ll
>5. //看是否存在 id_rsa 和 id_rsa.pub文件，如果存在，说明已经有SSH Key

* 如下图
  
![1.png](https://github.com/xander1010/test_dev/blob/master/pic/1.png)

* 如果没有SSH Key，则需要先生成一下
```
ssh-keygen -t rsa -C "xander1010@163.com"
执行后有提示,一个是让输入文件名,一个是密码,直接回车就好
```
* 执行之后继续执行以下命令来获取SSH Key
>1. cd ~/.ssh
>2. ls
>3. 或者
>4. ll
>5. //看是否存在 id_rsa 和 id_rsa.pub文件，如果存在，说明已经有SSH Key

## 三、获取SSH Key
>1. cat id_rsa.pub
>2. //拷贝秘钥 ssh-rsa开头

## 四、GitHub添加SSH Key
* GitHub点击用户头像，选择setting,新建一个SSH Key
  
# 五、验证和修改
```
ssh -T git@github.com
//运行结果出现类似如下
Hi xiang! You've successfully authenticated, but GitHub does not provide shell access.
```

# Git的使用
* 克隆项目
```shell
git clone https://github.com/xxxxx
```
* 查看状态
```shell
git status
```
* 提交给git管理
```shell
git add filename.py   //如果是.则是全部
```
* 版本提交
```shell
git commit -m "comment"
```
* 提交到远程仓库
```shell
git push origin master
```

## 分支项目
* dev master ...
  
* 查看当前分支
```shell
git branch -l
```
* 创建分支
```shell
git branch dev
```
* 切换分支
```shell
git checkout dev
```
* 合并分支（在master分支下将dev合并到master）
```shell
git merge dev
```

## 冲突处理
* pull拉取项目有冲突
```
git pull origin dev
From https://github.com/xxxxx
Auto-merging hello.py
CONFLICT xxxxxxxxx
```
* 提交冲突的文件
```
git add hello.py
git commit -m "comment change xxxx"
```
* 解决冲突
```
vim hello.py  //编辑文件并正确保存

git add hello.py
git commit -m 'comment' 
```

