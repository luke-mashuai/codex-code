# 拾味庭院

一个单页静态餐厅官网示例，包含首屏展示、晚市菜单、餐厅故事和到店信息。

## 项目结构

```text
.
├── assets/
│   └── restaurant-hero.svg
├── index.html
├── styles.css
└── README.md
```

## 本地预览

这是纯静态网页，可以直接在浏览器中打开 `index.html`。

也可以使用任意静态服务器预览，例如：

```bash
python -m http.server 8000
```

然后访问 `http://localhost:8000`。

## GitHub Pages 部署

仓库已包含 GitHub Actions 配置。推送到 `main` 分支后，可在 GitHub 仓库的
`Settings > Pages` 中选择 `GitHub Actions` 作为部署来源。

## 适合扩展的方向

- 接入真实订位系统或表单
- 增加菜单 JSON 数据源
- 添加移动端菜单导航
- 替换为真实餐厅照片资源
