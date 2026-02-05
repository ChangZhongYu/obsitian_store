Git 版本控制工具

三种工作区：

| 区域   | 文件状态     | 命令         | 说明     |
| ---- | -------- | ---------- | ------ |
| 工作区  | 已修改（未跟踪） | git add    | 加入暂存区  |
| 缓存区  | 已暂存      | git commit | 提交本地仓库 |
| 本地仓库 | 已提交      |            |        |

### 常用命令：

#### query

```bash
1. 查看本地分支：git branch
    
2. 查看远程分支：git branch -r
    
3. 查看所有分支（本地和远程）：git branch -a
   
4. 查看本地分支与远程分支的追踪关系：git branch -vv
   
# 获取文件状态
git status
   
# 查看提交日志
git log |--pretty=oneline 格式化展示
git log --graph --oneline --all -n 5

# 查看历史操作
git reflog

```
#### opertor

``` bash
# 提交并说明
git commit -m '说明' |-am 缓存并提交  

# 对比工作区文件和仓库文件
gti diff HEAD -- 对比文件名称

# 撤销暂存
git restore --staged 文件名

# 清除未跟踪的文件
git clean -f -d

# 撤销上一次命令
git reset HEAD 文件名（）

# 版本回退
git reset --hard HEAD^ | ^数量表示回退几个版本 | ~10 回退10个版本 

git reset --hard commitID 回退到指定ID的版本

# 切换分支
git checkout 分支名

# 删除分支
git branch -d|-D 分支名 -D强制删除

# 合并分支
gti merge 被合并的分支

# 配置SSH公钥 rsa 非对称秘钥算法 目录 cat ~/.ssh/id_rsa.pub
ssh-keygen -t rsa

# 查看配置是否成功
ssh -T git@仓库地址

# 配置远程仓库
git remote add 远程仓库名（origin） 地址

# 查看
git remote

# 推送
git push [-f][--set-upstream]仓库名 分支 [强制推送][对应关系，仓库名后加分支]

# 查看分支对应关系
git branch -vv

# 从远程仓库拷贝
git clone

# 抓取（更新不合并）
git fetch 

# 获取远程仓库origin的所有分支的更新
git fetch origin

# 拉取（合并本地代码）
git pull
```

**%% .gitignore 不管理的文件 %%**

---

### github推送命令

1. 初始化Git仓库            

```bash
git init

# 抓取远程分支
git pull origin main/master
```

2. 添加远程仓库地址

```bash
git remote add origin 仓库URL

# 更改
git remote set-url origin 仓库ssh
```

3. 将更改文件添加到缓存区

```bash
git add . | 具体文件名
```

4. 提交更改文件

```bash
git commit -m "提交说明"
```

5. 推送至远程仓库

```bash
git push -u origin main/master

# 强制推送
git push --force origin main
```

### GitHub拉取命令

1. 获取远程分支更新
```bash
git fetch origin main

# 新项目克隆
git clone URL
```
2. 合并分支
```bash
git pull
```

---

### 其他配置

```bash
# 查看远程地址
git remote -v

# 查看当前代理
git config --global --get http.proxy
git config --global --get https.proxy

# 设置代理
git config --global http.proxy http://127.0.0.1:7890
git config --global https.proxy http://127.0.0.1:7890

# 清除代理
git config --global --unset http.proxy
git config --global --unset https.proxy
```

在Idea中使用git
 1. 配置idea
 2. 初始化本地仓库
 3. 配置忽视文件
 4. 提交或推送