# 01 — Repository

## 1. 什么是 Repository？

Repository，简称 **Repo**，中文通常称为“仓库”。

一个 Git Repository 不只是普通文件夹，它包含：

1. 项目的实际文件
2. 文件修改历史
3. Commit 信息
4. Branch 信息
5. Git 配置信息
6. 与远程 Repository 的关系

例如：

```text
github-learning-repository/
│
├── README.md
├── notes/
│   └── 01-repository.md
│
└── .git/
```

其中 `.git/` 是 Git Repository 最关键的部分。

---

## 2. 普通文件夹和 Git Repository 的区别

普通文件夹主要保存：

```text
当前文件
```

Git Repository 除了保存当前文件，还记录：

```text
Version 1
   ↓
Version 2
   ↓
Version 3
   ↓
Current Version
```

因此可以查看：

- 文件什么时候修改
- 修改了哪些内容
- 谁进行了修改
- 为什么修改
- 以前的版本是什么

---

## 3. Local Repository 与 Remote Repository

Git Repository 可以存在于自己的电脑：

```text
Local Repository
```

也可以托管在 GitHub：

```text
Remote Repository
```

例如本项目：

```text
Mac
github-learning-repository
        ↕
GitHub
github-learning-repository
```

两者不是同一个文件夹。

Git 负责管理本地版本历史，而 GitHub 提供远程托管、同步和协作能力。

---

## 4. Clone

使用：

```bash
git clone <repository-url>
```

可以把 GitHub 上的 Repository Clone 到本地。

Clone 不只是下载项目文件，同时还会获取：

- `.git`
- Commit history
- Branch information
- Remote information

因此：

```text
Download ZIP
```

与：

```text
git clone
```

并不完全相同。

### Download ZIP

主要获得：

```text
当前项目文件
```

### git clone

获得：

```text
项目文件
+
Git Repository
+
版本历史
+
远程仓库关系
```

---

## 5. `.git`

运行：

```bash
ls -la
```

可以看到隐藏的：

```text
.git
```

`.git` 保存 Git Repository 的核心信息。

如果删除 `.git`：

```text
Git Repository
       ↓
普通文件夹
```

项目文件仍然存在，但 Git 的版本管理信息会消失。

---

## 6. `git status`

```bash
git status
```

用于查看当前 Repository 的状态。

例如：

```text
On branch main

nothing to commit, working tree clean
```

意味着：

- 当前位于 `main` branch
- 当前没有尚未记录的修改

这是 Git 中最常使用的命令之一。

当不知道目前 Repository 处于什么状态时，可以优先运行：

```bash
git status
```

---

## 7. Remote 与 origin

运行：

```bash
git remote -v
```

可以查看本地 Repository 连接的远程仓库。

例如：

```text
origin  https://github.com/username/github-learning-repository.git
```

`origin` 通常是 Git 为 Clone 来源设置的默认远程仓库名称。

可以简单理解为：

```text
origin
   ↓
GitHub Repository
```

---

## 8. Commit History

使用：

```bash
git log --oneline
```

可以查看 Commit 历史。

例如：

```text
a81c312 Update README
34f7a21 Initial commit
```

每个 Commit 都会拥有自己的 Commit ID。

Repository 因此不是只有“当前版本”，而是一系列可以追踪的历史状态。

---

## 9. 当前理解

Repository 可以理解为：

```text
Files
  +
Git History
  +
Branches
  +
Configuration
  +
Remote Relationship
```

GitHub Repository 则进一步加入：

```text
Remote Hosting
Issues
Pull Requests
Actions
Projects
Collaboration
```

---

## 10. 本节实际完成的操作

```bash
git clone
cd
ls
ls -la
git status
git remote -v
git log --oneline
mkdir
touch
```

本节最重要的认识：

> Repository 不是“放代码的文件夹”，而是一个带有完整版本历史和 Git 信息的项目。