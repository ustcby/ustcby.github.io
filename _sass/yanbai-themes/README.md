# Yanbai 主题库使用说明

## 6 套主题一览

| # | 主题名 | 风格 | 主色调 | 适用场景 |
|---|--------|------|--------|----------|
| 1 | **墨绿学术** (ink-green) | 深墨绿 + 米白，安静学术感 | `#1a6b5c` | 读书笔记、学术思考、长文阅读 |
| 2 | **暖棕编辑** (editorial) | 米白底 + 焦糖棕，杂志编辑风 | `#8b5e3c` | 文化评论、生活随笔、杂志感内容 |
| 3 | **北欧极简** (nordic) | 冷灰白底 + 雾蓝，Hygge 极简 | `#4a6fa5` | 科技笔记、产品思考、极简风格 |
| 4 | **暗夜学术** (dark-academic) | 深棕底 + 古铜金，学院暗夜风 | `#a67c52` | 深夜阅读、哲学思考、暗色系偏好 |
| 5 | **莫兰迪灰粉** (morandi-rose) | 米白底 + 灰粉/灰绿，低饱和高级感 | `#a67c8a` | 生活美学、文艺随笔、柔和风格 |
| 6 | **赛博科技** (cyber) | 深底 + 霓虹青/电光紫，科技感 | `#00d4aa` | 技术博客、AI/编程、极客风格 |

## 如何切换主题

### 方法一：直接编辑选择器（推荐）

1. 打开文件：`_sass/yanbai-themes/_selector.scss`
2. 找到你想要的主题那一行，**取消注释**（去掉行首的 `//`）
3. 把当前激活的主题那一行**加上注释**（在行首加 `//`）
4. 确保每次只有一个主题处于激活状态
5. 提交推送：
   ```bash
   git add .
   git commit -m "切换主题为 xxx"
   git push
   ```
6. 等待 GitHub Actions 构建完成（约1分钟），刷新网站即可

### 示例：切换到「暖棕编辑」

编辑前：
```scss
@import "yanbai-themes/ink-green";       // ← 当前激活
// @import "yanbai-themes/editorial";
```

编辑后：
```scss
// @import "yanbai-themes/ink-green";
@import "yanbai-themes/editorial";       // ← 新激活
```

## 每套主题包含什么

每套主题都完整定义了亮色 + 暗色双模式的以下变量：

- `--global-theme-color` — 主题色（链接、标题强调、边框）
- `--global-hover-color` — 悬停色
- `--global-text-color` — 正文颜色
- `--global-text-color-light` — 次要文字颜色
- `--global-divider-color` — 分割线颜色
- `--global-code-bg-color` — 行内代码背景
- `--global-bg-color` — 页面背景色
- `--yanbai-table-head-bg` — 表格表头渐变背景
- `--yanbai-table-stripe` — 表格斑马纹背景
- `--yanbai-table-hover` — 表格行悬停背景
- `--yanbai-blockquote-bg` — 引用块渐变背景
- `--yanbai-code-color` — 行内代码文字色
- `--yanbai-code-border` — 行内代码边框色

## 如何自定义/新增主题

1. 复制 `_sass/yanbai-themes/_ink-green.scss` 为新文件，如 `_my-theme.scss`
2. 修改其中的颜色值
3. 在 `_selector.scss` 中添加一行 `@import "yanbai-themes/my-theme";`
4. 取消注释即可使用

## 注意事项

- 切换主题后，网站右上角的暗色/亮色切换按钮仍然有效，每套主题都适配了两种模式
- 「暗夜学术」和「赛博科技」默认就是深色风格，亮色模式为暖米白/浅青色
- 表格、引用块、代码块、标签徽章等所有元素都会随主题自动变色
