# 拾味庭院

一个基于 Vue 3 + Vite 的单页餐厅首页示例，包含首屏展示、晚市菜单、餐厅故事和到店信息。

## 项目结构

```text
.
├── src/
│   ├── assets/
│   │   └── restaurant-hero.svg
│   ├── App.vue
│   ├── main.js
│   └── styles.css
├── index.html
├── package.json
└── README.md
```

## 本地开发

```bash
npm install
npm run dev
```

默认访问地址为 `http://127.0.0.1:5173`。

## 构建

```bash
npm run build
```

构建产物会输出到 `dist/`。

## GitHub Pages 部署

仓库已包含 GitHub Actions 配置。推送到 `main` 分支后，会自动安装依赖、构建 Vue 项目，并部署 `dist/`。
