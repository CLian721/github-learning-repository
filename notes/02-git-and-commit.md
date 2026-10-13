# 02 — Git Changes & Commit

## 1. Git 如何看待文件变化？

在 Git Repository 中，文件常见状态包括：

```text
Untracked
Modified
Staged
Committed
```

可以大致理解为：

```text
新文件
  ↓
Untracked
  ↓ git add
Staged
  ↓ git commit
Committed
```

对于 Git 已经管理的文件：

```text
Committed
  ↓ 修改
Modified
  ↓ git add
Staged
  ↓ git commit
新的 Committed Version
```

---

## 2. `git status`

```bash
git status
```

用于查看 Repository 当前状态。

它可以告诉我：

- 当前在哪个 Branch
- 哪些文件被修改
- 哪些文件尚未追踪
- 哪些修改已经进入 Staging Area
- 本地 Branch 与远程 Branch 是否同步

因此，当不确定 Git 当前状态时，优先使用：

```bash
git status
```

---

## 3. Modified 与 Untracked

### Modified

例如：

```text
modified: notes/01-repository.md
```

表示：

> Git 已经认识这个文件，但文件内容与最近一次 Commit 不同。

### Untracked

例如：

```text
notes/02-git-and-commit.md
```

表示：

> 这是新文件，Git 目前还没有正式追踪它。

---

## 4. `git diff`

```bash
git diff
```

用于查看：

> Working Directory 中尚未 Stage 的具体修改。

通常：

```diff
- 删除的内容
+ 新增的内容
```

因此 `git status` 回答：

> 哪些文件变了？

而 `git diff` 回答：

> 文件具体变了什么？

---

## 5. Staging Area

使用：

```bash
git add <file>
```

可以把修改放入 Staging Area。

例如：

```bash
git add notes/01-repository.md
git add notes/02-git-and-commit.md
```

Staging Area 可以理解为：

> 下一次 Commit 准备包含的内容。

因此：

```text
Working Directory
        ↓
     git add
        ↓
  Staging Area
        ↓
    git commit
        ↓
 Repository History
```

---

## 6. `git diff` 与 `git diff --staged`

修改文件但尚未 `git add` 时：

```bash
git diff
```

查看尚未 Stage 的修改。

执行 `git add` 后：

```bash
git diff --staged
```

查看已经进入 Staging Area、准备进入下一次 Commit 的修改。

可以记成：

```text
git diff
=
我改了什么，但还没选进 Commit？

git diff --staged
=
我已经选了什么，准备 Commit？
```

---

## 7. Commit

```bash
git commit -m "Commit message"
```

Commit 会把 Staging Area 中的内容保存为 Repository 历史中的一个版本。

可以把 Commit 理解为一个：

> 有说明文字的项目快照。

例如：

```text
Commit A
Initial repository

      ↓

Commit B
Add repository notes

      ↓

Commit C
Add Git and commit notes
```

---

## 8. Commit Message

一个好的 Commit Message 应该简短说明：

> 这次修改完成了什么？

例如：

```text
Add notes on Git and commits
```

比：

```text
update
```

更有意义。

以后查看：

```bash
git log --oneline
```

就能快速理解项目历史。

---

## 9. `git log`

```bash
git log --oneline
```

用于简洁查看 Commit History。

例如：

```text
7da9132 Add notes on Git and commits
4af3181 Add notes on GitHub repositories
128caf0 Update README with GitHub learning roadmap
```

每一行代表一个 Commit。

---

## 10. Git 的核心思想

Git 并不是简单记录：

```text
文件最终长什么样
```

而是在记录：

```text
Version A
   ↓
发生一次有意义的修改
   ↓
Version B
   ↓
发生下一次修改
   ↓
Version C
```

因此好的 Git 使用习惯通常是：

```text
完成一组相关修改
        ↓
检查修改
        ↓
Stage
        ↓
Commit
```

而不是积累大量无关修改后一次全部 Commit。