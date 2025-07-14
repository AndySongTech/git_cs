在 Git 中，文件的生命周期可以分为几个**关键状态**，理解这些状态有助于你更清晰地掌握版本控制的流程。

---

## 🧭 Git 的四个主要状态

| 状态 | 说明 | 常见命令 |
|------|------|----------|
| **Working Directory**（工作区） | 你当前项目的实际文件夹，包含你正在编辑的文件。 | `git status` 查看哪些文件被修改 |
| **Staging Area**（暂存区 / 索引） | 你用 `git add` 标记为“准备提交”的更改。 | `git add <file>` 把更改放入暂存区 |
| **Repository**（本地仓库） | 你用 `git commit` 提交的历史记录，保存在 `.git` 目录中。 | `git commit -m "message"` 提交更改 |
| **Remote Repository**（远程仓库） | 比如 GitHub、GitLab 上的仓库。你需要用 `git push` 把本地提交推送上去。 | `git push origin <branch>` |

---

## 🔄 文件状态转换图（简化版）

```
修改文件
   ↓
Working Directory
   ↓ git add
Staging Area
   ↓ git commit
Repository (本地)
   ↓ git push
Remote Repository
```

---

## 🧪 示例

假设你修改了 `app.js`：

1. **修改后未添加**：`app.js` 处于 Working Directory 状态。
2. **执行 `git add app.js`**：它进入 Staging Area。
3. **执行 `git commit -m "update"`**：它被记录到本地仓库。
4. **执行 `git push`**：它被同步到远程仓库。
