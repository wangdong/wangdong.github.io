# 图片存放说明

## 目录结构
```
static/images/
├── 2024/           # 2024年文章图片
├── 2025/           # 2025年文章图片
├── common/         # 通用图片（头像、logo等）
└── README.md       # 本说明文件
```

## 使用方式

### 简单引用
```markdown
![图片描述](/images/2025/article-name/image.png)
```

### 带标题和链接
```markdown
![图片描述](/images/2025/article-name/image.png "图片标题")
```

### 控制大小（PaperMod主题支持）
```markdown
{{< figure src="/images/2025/article-name/image.png" title="图片标题" width="600" >}}
```

## 建议
- 图片文件名使用英文，避免中文
- 每篇文章的图片放在独立子目录
- 图片格式推荐：PNG（截图）、JPG（照片）、WebP（优化）
- 图片大小控制在1MB以内