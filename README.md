# Blog_Archive

这是博客程序仓库（Fuwari 分支）的内容数据仓库，通过 `scripts/sync-content.js` 在构建前同步到 `content/` 目录。跟代码分开管理，方便博客程序单独升级、也方便其他人 Fork 走博客程序本身而不必带上这里的内容。

## 目录结构

```
posts/       文章 Markdown 文件
friends/     友链数据（独立 JSON，一个文件一条友链）
  _order.json  友链的显示顺序（文件名列表，不在此列表中的排在最后）
projects/    项目展示数据（独立 JSON，一个文件一个项目）
  _order.json  项目的显示顺序，用法同上
```

## 格式说明

- `posts/*.md`：frontmatter 字段参考博客程序仓库里 `src/content.config.ts` 的 `postsCollection` schema（`title`、`published`、`tags`、`draft` 等）。
- `friends/*.json`：字段为 `name`、`url`、`avatar`、`introduction`、`friendsPage`，文件名即该友链的 id。
- `projects/*.json`：字段参考 `projectsCollection` schema（`title`、`description`、`category`、`techStack`、`status`、`sourceCode`、`visitUrl`、`featured` 等），文件名即该项目的 id。

新增/删除内容时记得同步更新对应的 `_order.json`。
