# 04 — Branch & Merge

## What is a Branch?

Branch 是 Git 中的一条独立开发线。

创建 Branch 后，可以在不直接影响 `main` 的情况下：

- 修改文件
- 创建文件
- Commit
- 测试新功能
- 尝试不同方案

一个简单的结构可以表示为：

```text
A --- B --- C
            \
             D --- E
```

其中：

```text
main              → C
learn-branch      → E
```

---

## Why use Branches?

Branch 可以让不同工作彼此隔离。

例如：

```text
main
├── fix-bug
├── new-feature
└── experiment
```

这样可以避免直接在稳定的 `main` 分支上进行实验性修改。

---

## Basic Commands

查看所有本地 Branch：

```bash
git branch
```

创建并切换到新 Branch：

```bash
git switch -c branch-name
```

切换 Branch：

```bash
git switch branch-name
```

合并 Branch：

```bash
git merge branch-name
```

删除已经完成的本地 Branch：

```bash
git branch -d branch-name
```

---

## Basic Branch Workflow

```text
main
 ↓
create branch
 ↓
edit files
 ↓
git add
 ↓
git commit
 ↓
switch to main
 ↓
git merge
 ↓
delete branch
```

对应命令：

```bash
git switch -c learn-branch
git add .
git commit -m "Add branch learning notes"

git switch main
git merge learn-branch

git branch -d learn-branch
```

---

## Merge

Merge 用于把一个 Branch 中的修改合并到另一个 Branch。

例如：

```text
main
A --- B --- C

learn-branch
             \
              D
```

在 `main` 上执行：

```bash
git merge learn-branch
```

之后 `learn-branch` 中完成的修改就会进入 `main`。

---

## Important Idea

Branch 并不是复制整个项目。

Branch 本质上是：

> 一个指向 Git Commit 的可移动引用。

创建 Branch 后，不同 Branch 可以逐渐指向不同的 Commit。

---

## What I Practiced

在 `github-learning-repository` 中：

1. 从 `main` 创建 `learn-branch-merge`
2. 切换到该 Branch
3. 创建 `notes/04-branch.md`
4. 在 Branch 中 Commit
5. 切回 `main`
6. Merge `learn-branch-merge`
7. Push 更新后的 `main`
8. 删除已经完成的 Branch

通过这个过程实际理解 Branch 与 Merge。