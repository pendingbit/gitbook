# Command

### 一、安装与配置

#### 1. 安装 Git

* [Git 官方下载](https://git-scm.com/downloads)：根据操作系统下载并安装。
*   检查是否安装成功：

    ```bash
    git --version
    ```

#### 2. 基本配置

*   设置用户名和邮箱（提交时记录身份）：

    ```bash
    git config --global user.name "Your Name"
    git config --global user.email "you@example.com"
    ```
*   查看当前配置：

    ```bash
    git config --list
    ```
*   配置文本编辑器（可选）：

    ```bash
    git config --global core.editor "vim"  # 或 nano、code 等
    ```

***

### 二、创建与初始化项目

#### 1. 初始化仓库

*   初始化一个 Git 仓库：

    ```bash
    git init
    ```
*   将已有代码纳入版本控制：

    ```bash
    git add .
    git commit -m "Initial commit"
    ```

#### 2. 克隆远程仓库

*   克隆一个已有仓库：

    ```bash
    git clone <仓库地址>
    ```

***

### 三、基本操作

#### 1. 查看状态

*   查看当前工作目录状态：

    ```bash
    git status
    ```

#### 2. 添加文件

*   添加单个文件：

    ```bash
    git add <文件名>
    ```
*   添加所有更改：

    ```bash
    git add .
    ```

#### 3. 提交更改

*   提交带描述的更改：

    ```bash
    git commit -m "描述信息"
    ```
*   提交包含详细信息的更改：

    ```bash
    git commit
    ```

#### 4. 查看历史记录

*   查看提交历史：

    ```bash
    git log
    ```
*   简化历史记录显示：

    ```bash
    git log --oneline --graph --all
    ```

***

### 四、分支操作

#### 1. 创建分支

*   创建新分支：

    ```bash
    git branch <分支名>
    ```
*   切换到新分支：

    ```bash
    git checkout <分支名>
    ```
*   创建并切换分支：

    ```bash
    git checkout -b <分支名>
    ```

#### 2. 合并分支

*   切换到目标分支并合并：

    ```bash
    git checkout <目标分支>
    git merge <源分支>
    ```

#### 3. 删除分支

*   删除本地分支：

    ```bash
    git branch -d <分支名>
    ```
*   强制删除：

    ```bash
    git branch -D <分支名>
    ```

***

### 五、远程操作

#### 1. 查看远程仓库

*   查看当前远程仓库：

    ```bash
    git remote -v
    ```

#### 2. 添加远程仓库

*   添加远程仓库：

    ```bash
    git remote add origin <仓库地址>
    ```

#### 3. 推送代码

*   推送代码到远程分支：

    ```bash
    git push origin <分支名>
    ```

#### 4. 拉取代码

*   从远程仓库更新代码：

    ```bash
    git pull origin <分支名>
    ```

***

### 六、高级功能

#### 1. 回滚更改

*   恢复暂存区的文件到工作区：

    ```bash
    git restore <文件名>
    ```
*   恢复整个暂存区：

    ```bash
    git restore --staged .
    ```
*   重置到某次提交（保留更改）：

    ```bash
    git reset <提交ID>
    ```
*   强制重置（丢弃更改）：

    ```bash
    git reset --hard <提交ID>
    ```

#### 2. 查看差异

*   查看工作区与暂存区的差异：

    ```bash
    git diff
    ```
*   查看暂存区与上一次提交的差异：

    ```bash
    git diff --staged
    ```

#### 3. 标签管理

*   创建标签：

    ```bash
    git tag <标签名>
    ```
*   查看标签：

    ```bash
    git tag
    ```
*   推送标签到远程：

    ```bash
    git push origin <标签名>
    ```

***

### 七、协作流程（常见工作流）

#### 1. 基本协作流程

1.  克隆仓库：

    ```bash
    git clone <仓库地址>
    ```
2.  创建分支开发：

    ```bash
    git checkout -b feature/<功能名>
    ```
3.  提交代码：

    ```bash
    git add .
    git commit -m "完成功能开发"
    ```
4.  推送到远程：

    ```bash
    git push origin feature/<功能名>
    ```
5. 提交 Pull Request，代码审核通过后合并。

#### 2. Rebase 操作

*   合并提交历史：

    ```bash
    git rebase <分支名>
    ```
*   解决冲突后继续：

    ```bash
    git rebase --continue
    ```

***

### 八、常见问题解决

#### 1. 忘记添加 `.gitignore`

*   修改 `.gitignore` 后清理缓存：

    ```bash
    git rm -r --cached .
    git add .
    git commit -m "更新 .gitignore"
    ```

#### 2. 撤销最近一次提交（保留更改）：

```bash
git reset --soft HEAD~1
```

#### 3. 强制推送代码（谨慎使用）：

```bash
git push origin <分支名> --force
```

***

