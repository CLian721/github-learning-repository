# GitHub Learning Repository

A hands-on repository for learning **Git**, **GitHub**, and collaborative development workflows.

这个仓库用于记录我系统学习 GitHub 的过程。与单纯阅读教程不同，本仓库中的 GitHub 功能会尽可能通过实际操作来学习和记录。

---

## 🎯 Learning Goals

通过这个仓库，我希望逐步理解并实际掌握：

- Git 与 GitHub 的区别
- Repository 的基本结构
- Markdown 与 README
- Git 的版本控制思想
- Commit 与版本历史
- Clone、Push 和 Pull
- Branch 与 Merge
- Issues
- Pull Requests
- Fork
- Tags 与 Releases
- `.gitignore`
- LICENSE
- GitHub Projects
- GitHub Actions
- GitHub 的基本协作流程

---

## 🗺️ Learning Roadmap

| Stage | Topic | Status |
|---|---|---|
| 01 | Repository | ✅ Completed |
| 02 | README & Markdown | ✅ Completed |
| 03 | Git & Commit | ✅ Completed |
| 04 | Clone / Push / Pull | ⬜ Not started |
| 05 | Branch & Merge | ⬜ Not started |
| 06 | Issues | ⬜ Not started |
| 07 | Pull Requests | ⬜ Not started |
| 08 | Fork | ⬜ Not started |
| 09 | `.gitignore` | ⬜ Not started |
| 10 | License | ⬜ Not started |
| 11 | Tags & Releases | ⬜ Not started |
| 12 | GitHub Projects | ⬜ Not started |
| 13 | GitHub Actions | ⬜ Not started |

---

## 📁 Repository Structure

随着学习进行，这个仓库会逐步形成下面的结构：

```text
github-learning-repository/
│
├── README.md
│
├── notes/
│   ├── 01-repository.md
│   ├── 02-git-and-commit.md
│   ├── 03-clone-push-pull.md
│   ├── 04-branch.md
│   ├── 05-issue.md
│   ├── 06-pull-request.md
│   ├── 07-fork.md
│   ├── 08-release-tag.md
│   └── 09-github-actions.md
│
├── practice/
│   ├── hello-github.txt
│   └── learning-log.md
│
├── .gitignore
├── LICENSE
│
└── .github/
    └── workflows/
```

这些文件不会一次性创建，而会随着对应 GitHub 功能的学习逐步加入。

---

## 🧠 Core Concepts

### Git

Git 是一个**版本控制系统**。

它主要负责：

- 记录文件修改
- 保存历史版本
- 创建分支
- 合并修改
- 回退版本

Git 可以完全在本地电脑上工作，并不依赖 GitHub。

### GitHub

GitHub 是建立在 Git 基础上的在线协作平台。

它提供：

- 远程 Repository
- 代码托管
- Issues
- Pull Requests
- Projects
- Actions
- Releases
- 团队协作
- 开源社区

因此可以简单理解为：

```text
Git
负责版本控制

        +

GitHub
负责托管、同步和协作
```

---

## 🔄 Basic Workflow

未来最常使用的基本工作流程是：

```text
GitHub Repository
        ↓
      Clone
        ↓
Local Repository
        ↓
    Edit files
        ↓
      git add
        ↓
    git commit
        ↓
     git push
        ↓
GitHub Repository
```

多人协作时还会加入：

```text
Issue
  ↓
Branch
  ↓
Commit
  ↓
Push
  ↓
Pull Request
  ↓
Review
  ↓
Merge
```

---

## 📝 Learning Principle

这个仓库遵循一个原则：

> Learn GitHub by using GitHub.

每学习一个概念，都尽量在这个 Repository 中完成一次真实操作，并留下对应的历史记录。

因此，这个仓库本身既是：

- 学习笔记
- Git 练习项目
- GitHub 功能实验场
- 版本历史示例
- 可分享的 GitHub 入门资料

---

## 📚 Progress

### Completed

- [x] Create a GitHub repository
- [x] Initialize the repository with a README

### Next

- [x] ] Learn Markdown
- [x] ] Understand commits
- [ ] Clone this repository to a local computer
- [ ] Make the first local commit
- [ ] Push changes to GitHub

---

## 📌 Repository Purpose

这个仓库不会用于正式软件开发，而主要用于理解 Git 和 GitHub 的工作方式。

学习完成后，希望能够独立完成：

```text
Create Repository
        ↓
Clone
        ↓
Edit
        ↓
Commit
        ↓
Push
        ↓
Branch
        ↓
Pull Request
        ↓
Merge
```

并能够阅读和参与其他 GitHub 开源项目。
