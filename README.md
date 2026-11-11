# sjmmap — 任务流程编辑器

轻量级网页任务流程编辑器：单文件 `index.html`，零依赖（无需构建），双击即可使用。

## 功能

- **添加节点**：卡片可编辑 TaskName / MemThread / Params（微软雅黑，自动换行）
- **连线**：卡片左右任一端口拖到目标卡片即生成箭头连线
- **拖动 / 多选**：卡片自由拖动，Shift 框选、Ctrl+点击多选，Delete 批量删除
- **上下游高亮**：选中任务后自动标绿上游、标橙下游，连线与箭头同步变色
- **一键重排**：最长路径分层自动布局（容忍环），动画过渡
- **撤销 / 重做**：Ctrl+Z / Ctrl+Y，覆盖增删、连线、拖动、重排、导入
- **导入 / 导出 JSON**：与 React Flow 导出格式完全兼容，导出可自定义文件名
- 自动保存到 localStorage，刷新不丢失

## 使用

直接用浏览器打开 `index.html`，或访问在线部署地址。

## 部署到 Netlify（从 GitHub）

仓库已含 `netlify.toml`（发布目录 = 根目录，无需构建命令），连接后开箱即用：

1. 打开 [app.netlify.com](https://app.netlify.com)，登录后进入 **Sites → Add new site → Import an existing project**；
2. 选择 **Deploy with GitHub**，授权并选中本仓库 `sjmmap`；
3. 部署设置无需改动（构建命令留空、发布目录 `.` 已由 `netlify.toml` 指定），直接点 **Deploy**；
4. 完成后得到 `https://<随机名>.netlify.app`，可在 Site settings → Change site name 改名；
5. 之后每次 `git push` 到 `main`，Netlify 会自动重新部署。

也可使用 Netlify CLI：`npx netlify deploy --prod --dir .`

