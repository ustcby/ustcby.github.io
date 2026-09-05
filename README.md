# Yanbai · 每日思考花园

个人网站：每日思考 · 读书笔记 · 资源库。

- **域名**: `https://ustcby.github.io`
- **主题**: [al-folio](https://github.com/alshedivat/al-folio)（Jekyll，MIT）
- **托管**: GitHub Pages（免费）

## 快速上手

### 首次部署（10 分钟）

1. **创建仓库**：在 GitHub 新建仓库，名字填 `ustcby.github.io`（必须是这个，GitHub Pages 用户站点的硬规则），Public，**不要**勾选 README。
2. **上传内容**：把本目录下所有文件上传到该仓库（GitHub 网页端 `Add file → Upload files` 即可，拖入即可）。
3. **等待发布**：仓库 `Settings → Pages`，Source 选择 `GitHub Actions`（构建由仓库内 `.github/workflows/deploy.yml` 自动完成），保存。约 2-3 分钟后站点上线。
4. **验证**：浏览器打开 `https://ustcby.github.io`，看到"首页"即成功。

> 注意：GitHub Pages 用户站点要求仓库名必须等于用户名（`ustcby.github.io`），否则不会托管。

### 日常更新（每天 5 分钟）

写一篇新的每日思考：

1. 在 `_posts/` 目录新建文件，命名 `YYYY-MM-DD-标题.md`（日期必须是当天，否则不会显示在最新列表）
2. 复制任意一篇现有文章的 frontmatter 开头，改标题和日期：
   ```yaml
   ---
   layout: post
   title: 你的标题
   date: 2026-09-05 09:00:00 +0800
   description: 一句话摘要（会显示在列表页）
   tags: 思考 读书
   categories: 每日思考
   related_posts: true
   ---
   ```
3. 正文用 Markdown 写，支持数学公式（`$$...$$`）、代码高亮、图片
4. 上传到仓库（网页端拖入 `_posts/` 即可），等待 1-2 分钟自动发布

## 内容结构

| 路径 | 作用 |
|---|---|
| `_posts/` | 所有文章（每日思考、读书笔记等），按日期归档 |
| `_pages/about.md` | 首页（关于页），改你的介绍 |
| `_pages/blog.md` | 每日思考列表页 |
| `assets/img/prof_pic.jpg` | 首页头像（替换成你自己的照片，正方形最佳） |
| `_config.yml` | 站点全局配置（标题、邮箱、社交链接） |

## 可选的进阶配置（都写在 _config.yml）

- **社交链接**：GitHub（已填 `ustcby`）、X、邮箱等，在 `_config.yml` 的 Social integration 段取消注释填入即可
- **评论区**：al-folio 支持 Giscus（GitHub 讨论区评论），在 `_config.yml` 的 `giscus:` 段按 https://giscus.app 指引配置
- **订阅**：RSS 已内置，地址 `https://ustcby.github.io/feed.xml`
- **暗黑模式**：页面右上角可切换，已默认开启
- **自定义域名**（可选）：买一个域名后，在仓库根目录加 `CNAME` 文件，内容写你的域名

## 关于主题

基于 [al-folio](https://github.com/alshedivat/al-folio) v0.12+（Jekyll 学术主题），已做如下定制：

- 站点身份改为 `Yanbai` / `ustcby` / 中文语言
- 导航精简为「首页 + 每日思考」，隐藏学术导向页面（news/cv/projects/publications/teaching 等文件保留，nav 已关闭，随时可重新开启）
- 清空全部示例文章/新闻/项目/图片，替换为 4 篇示例内容（3 篇每日思考 + 1 篇读书笔记模板）
- 博客页展示标签/分类改为中文（思考、AI、读书、决策、职业 / 每日思考、读书笔记）
