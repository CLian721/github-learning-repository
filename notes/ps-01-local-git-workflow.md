# 02 — Local Git Workflow

本节记录第一次在 Mac 本地完成 Git 修改、暂存、提交和推送的完整流程。

---

## 1. 查看文件状态

修改或新建文件后，先运行：

```bash
git status
```

如果出现：

```text
Untracked files:
    notes/01-repository.md
```

说明：

> 文件已经存在于电脑中，但 Git 还没有开始追踪它。

`git status` 是最常用的 Git 命令之一，不确定当前仓库状态时可以优先运行它。

---

## 2. `git add`：加入暂存区

运行：

```bash
git add notes/01-repository.md
```

再次查看：

```bash
git status
```

文件会从：

```text
Untracked files
```

变为：

```text
Changes to be committed
```

说明文件已经进入：

```text
Working Directory
        ↓ git add
Staging Area
```

### Staging Area

暂存区可以理解为：

> 选择哪些修改要进入下一次 Commit。

因此：

```text
git add ≠ 上传 GitHub
git add ≠ 创建版本
```

它只是选择准备提交的修改。

---

## 3. `git commit`：创建本地版本

运行：

```bash
git commit -m "Add notes on GitHub repositories"
```

其中：

```text
-m
```

表示为这次 Commit 添加说明。

Commit 可以理解为：

> 为当前选中的修改创建一个有说明的历史版本。

基本流程：

```text
修改文件
   ↓
git add
   ↓
Staging Area
   ↓
git commit
   ↓
Local Repository
```

---

## 4. Git 用户身份

第一次 Commit 时，Git 可能提示：

```text
Author identity unknown
```

因为 Git 需要记录：

> 这次 Commit 是谁创建的？

可以设置：

```bash
git config --global user.name "GitHub用户名"
```

以及：

```bash
git config --global user.email "邮箱"
```

设置完成后重新执行 Commit 即可。

---

## 5. Commit 不等于上传 GitHub

Commit 后运行：

```bash
git status
```

可能看到：

```text
Your branch is ahead of 'origin/main' by 1 commit.
```

这说明：

```text
Local main
    │
    ● 新 Commit
    │
    ● 旧 Commit

GitHub origin/main
    │
    ● 旧 Commit
```

新的 Commit 目前只存在于本地电脑。

因此：

```text
git commit
```

只是记录到：

```text
Local Repository
```

而不是上传到 GitHub。

---

## 6. `git push`：上传到 GitHub

运行：

```bash
git push origin main
```

可以理解为：

```text
git push
= 上传本地 Commit

origin
= GitHub 远程仓库

main
= 要上传的 Branch
```

因此：

```text
Local main
     ↓ git push
GitHub main
```

---

## 7. GitHub HTTPS 登录

第一次通过 HTTPS 执行 `git push` 时，Terminal 可能询问：

```text
Username for 'https://github.com':
```

输入 GitHub 用户名。

然后可能出现：

```text
Password for 'https://用户名@github.com':
```

这里不能使用普通 GitHub 登录密码。

需要使用：

```text
Personal Access Token
```

即 PAT。

可以把 PAT 简单理解为：

> GitHub 为命令行或其他程序提供的专用访问凭证。

创建 Token 时，只给当前需要的 Repository 和必要权限即可，例如：

```text
Repository:
github-learning-repository

Contents:
Read and write
```

### 注意

输入 Token 时，Terminal 通常不会显示：

```text
*****
```

甚至看起来完全没有输入内容，这是正常现象。

输入完成后直接按 Enter。

Token 属于敏感信息，不应该：

- 上传到 GitHub
- 写入代码
- 发给别人
- 放进 README

---

## 8. Push 成功

成功执行：

```bash
git push origin main
```

后，Terminal 通常会出现：

```text
main -> main
```

此时本地版本已经同步到 GitHub。

刷新 Repository 页面即可看到：

```text
README.md
notes/
    01-repository.md
```

同时 Commit history 中也会出现刚刚创建的新 Commit。

---

## 9. 完整工作流程

本节最重要的是理解下面这条链：

```text
编辑文件
   ↓
Working Directory
   ↓
git add
   ↓
Staging Area
   ↓
git commit
   ↓
Local Repository
   ↓
git push
   ↓
Remote Repository (GitHub)
```

三个核心命令可以简单记成：

```text
git add
修改 → 暂存区

git commit
暂存区 → 本地版本历史

git push
本地版本历史 → GitHub
```

---

## 10. 常用检查命令

### 查看当前状态

```bash
git status
```

### 查看简洁 Commit 历史

```bash
git log --oneline
```

### 查看远程仓库

```bash
git remote -v
```

---

## 11. 本节实际完成的操作

```bash
git status
git add notes/01-repository.md
git commit -m "Add notes on GitHub repositories"
git push origin main
```

同时实际接触了：

- Untracked files
- Staging Area
- Commit
- Local Repository
- Remote Repository
- `origin/main`
- Git 用户身份
- HTTPS 认证
- Personal Access Token

---

## 12. 本节最重要的认识

Git 的工作方式不是：

```text
修改
↓
上传
```

而是：

```text
修改
↓
选择修改
↓
记录版本
↓
同步远程
```

即：

```text
Edit
 ↓
git add
 ↓
git commit
 ↓
git push
```

这也是之后绝大多数 Git 工作流的基础。