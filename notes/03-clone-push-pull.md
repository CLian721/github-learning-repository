# 03 — Clone, Fetch, Pull & Push

## 1. Local 与 Remote

一个 GitHub 项目通常同时存在：

```text
Local Repository
        ↕
Remote Repository
```

例如：

```text
Mac
main

GitHub
origin/main
```

它们并不会自动实时同步。

---

## 2. Clone

```bash
git clone <repository-url>
```

用于第一次把 Remote Repository 建立成本地 Repository。

Clone 会获得：

- 项目文件
- Commit History
- Branch 信息
- `.git`
- Remote 配置

并通常建立：

```text
origin
```

作为 GitHub Remote Repository 的默认名称。

---

## 3. Push

```bash
git push
```

用于把本地已经 Commit 的内容发送到 Remote Repository。

流程：

```text
Working Directory
       ↓ git add
Staging Area
       ↓ git commit
Local Repository
       ↓ git push
Remote Repository
```

因此：

```text
git commit
```

并不等于：

```text
上传 GitHub
```

Commit 首先发生在本地。

---

## 4. `origin/main`

可以简单理解：

```text
main
=
本地工作的 main Branch

origin/main
=
本地记录的远程 main Branch 状态
```

需要注意：

`origin/main` 并不意味着 GitHub 正在实时连接本地电脑。

只有执行类似：

```bash
git fetch
```

之后，本地才会获取远程最新状态。

---

## 5. Fetch

```bash
git fetch origin
```

用于获取远程 Repository 的最新信息。

它会更新：

```text
origin/main
```

但不会直接把修改合并到：

```text
main
```

因此 Fetch 适合：

> 先查看远程发生了什么，再决定是否合并。

---

## 6. Pull

```bash
git pull
```

可以简单理解为：

```text
git fetch
+
git merge
```

即：

```text
GitHub
   ↓
Fetch
   ↓
origin/main
   ↓
Merge
   ↓
main
```

用于把 Remote Repository 的更新同步到当前本地 Branch。

---

## 7. Push 与 Pull

方向可以记成：

```text
             push
Local  ----------------> GitHub

Local  <---------------- GitHub
             pull
```

即：

```text
push
=
把我的 Commit 推出去

pull
=
把远程 Commit 拉回来
```

---

## 8. 常见日常工作流程

开始工作前：

```bash
git status
git pull
```

修改文件后：

```bash
git status
git diff
git add <files>
git diff --staged
git commit -m "message"
git push
```

因此完整流程可以表示为：

```text
git pull
   ↓
Edit
   ↓
git status
   ↓
git diff
   ↓
git add
   ↓
git diff --staged
   ↓
git commit
   ↓
git push
```

---

## 9. 当前理解

GitHub 与本地 Git 并不是一个实时同步的共享文件夹。

它们更像两个拥有各自 Commit History 的 Repository：

```text
Local Repository
       ↕
交换 Commit
       ↕
Remote Repository
```

Git 的同步本质上是在：

> 不同 Repository 之间交换和整合 Commit。