# CLAUDE.md

本文件为 Claude Code (claude.ai/code) 在此仓库中工作时提供指导。

## 仓库概述

这是一个使用 Hugo 静态站点生成器构建的个人博客/网站，采用 PaperMod 主题。网站使用中文编写，托管在 GitHub Pages 上，地址为 https://wangdong.github.io。

## 常用开发命令

### 本地开发
```bash
# 启动本地开发服务器（支持实时重载）
hugo server

# 构建站点（在 public/ 目录生成静态文件）
hugo

# 使用压缩和垃圾回收构建
hugo --gc --minify
```

### 内容管理
```bash
# 创建新文章（中文文章使用中文文件名）
hugo new posts/一切工作都是知识工作.md

# 创建新页面
hugo new page-name.md
```

### 部署
当推送更改到 `master` 分支时，站点会通过 GitHub Actions 自动部署到 GitHub Pages。

## 架构概览

### 目录结构
- `content/` - 所有 markdown 内容文件
  - `posts/` - 博客文章
  - `about.md`, `books.md`, `posts.md` - 静态页面
- `static/images/` - 按年份组织的图片
- `themes/PaperMod/` - 主题（Git 子模块）
- `layouts/partials/` - 自定义布局覆盖
- `i18n/` - 中文语言自定义
- `hugo.toml` - 主配置文件

### 关键配置（hugo.toml）
- 基础 URL：https://wangdong.github.io
- 语言：中文（zh-cn）
- 主题：PaperMod（含自定义配置）：
  - 禁用功能：分享按钮、目录、代码复制按钮
  - 中文日期格式自定义
  - 菜单项：文章、书籍、关于

### 自动化部署
GitHub Actions 工作流（`.github/workflows/hugo.yml`）处理：
- 安装 Hugo v0.147.8 和 Dart Sass
- 使用生产标志构建站点
- 部署到 GitHub Pages

### 内容格式
文章遵循 Hugo 标准的 front matter 格式：
```yaml
---
title: "文章标题"
date: 2024-01-01
draft: false
---
```
注意：不要给文章添加 tags 标签

## 开发注意事项

- PaperMod 主题作为 Git 子模块包含 - 使用 `git clone --recursive` 或 `git submodule update --init --recursive`
- 图片应放置在 `static/images/{年份}/` 目录
- 站点使用中文日期格式（例如："2024年1月1日"）
- 未使用测试框架 - 这是一个静态内容站点
- 中文文章使用中文文件名，无需转换为英文或拼音

## 发布

- 推送到远端即等价于发布
- 在每次发布前，请更新"目录.md"这个文件，目录中的内容按照时间排序，最新的在最前面