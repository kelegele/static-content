# kelegele-static-content

可了个乐 Docs 官方文档站点

## 快速开始

```bash
# 安装 Hugo
# Windows: choco install hugo-extended
# macOS: brew install hugo
# Linux: apt install hugo

# 初始化子模块（主题）
git submodule update --init --recursive

# 本地开发
hugo server

# 构建生产版本
hugo
```

## 项目结构

```
├── content/          # Markdown 内容
│   ├── easecall/     # 不纠结 App 相关页面
│   └── vocab-card/   # 单词卡片相关页面
├── layouts/          # 自定义布局模板
├── static/           # 静态资源
├── assets/           # CSS/JS 资源
└── themes/           # Hugo 主题（hugo-pure）
```

## 部署

构建产物在 `public/` 目录，可部署到任意静态托管服务。
