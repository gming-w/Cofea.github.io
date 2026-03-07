# NotionNext 迁移指南

## ✅ 已完成的配置

1. ✅ 克隆 NotionNext 项目到 `D:/code/blog-notionnext`
2. ✅ 配置环境变量（.env.local）
3. ✅ 添加自定义域名 CNAME 文件
4. ⏳ 正在安装依赖...

## 📋 下一步操作

### 步骤 1：等待依赖安装完成

依赖安装正在后台运行，大约需要 3-5 分钟。

### 步骤 2：本地测试

安装完成后，运行：

```bash
cd D:/code/blog-notionnext
npm run dev
```

访问 http://localhost:3000 查看效果。

### 步骤 3：推送到 GitHub

```bash
cd D:/code/blog-notionnext

# 删除原有的 git 配置
rm -rf .git

# 初始化新的 git 仓库
git init
git add .
git commit -m "feat: 迁移到 NotionNext

- 使用 NotionNext 作为博客系统
- 配置 Notion 集成
- 保留自定义域名 www.gming.space

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>"

# 添加远程仓库
git remote add origin https://github.com/Cofea/Cofea.github.io.git

# 强制推送（会覆盖现有代码）
git branch -M main
git push -u origin main --force
```

### 步骤 4：等待自动部署

推送后，GitHub Actions 会自动：
1. 同步 Notion 内容
2. 构建静态站点
3. 部署到 GitHub Pages

大约 3-5 分钟后，访问 https://www.gming.space 查看新博客！

## 🎨 主题配置

NotionNext 支持多种主题，在 `.env.local` 中修改：

```bash
# 可选主题：
# hexo - 类似 Hexo 的主题（当前使用）
# medium - Medium 风格
# next - 简洁现代风格
# nobelium - 优雅简约风格
# fukasawa - 日系风格
# gitbook - GitBook 风格
# matery - 多彩卡片风格

NEXT_PUBLIC_THEME=hexo
```

修改后重新构建即可。

## 📚 更多配置

详细配置请参考：
- NotionNext 文档：https://docs.tangly1024.com/
- 主题预览：https://preview.tangly1024.com/

## ⚠️ 注意事项

1. **Notion 数据库格式**：NotionNext 使用的是 Notion 页面 ID，而不是数据库 ID
2. **自定义域名**：已配置 www.gming.space，HTTPS 会自动启用
3. **GitHub Actions**：NotionNext 自带的工作流会自动处理部署

## 🔄 回滚方案

如果需要回滚到原来的博客系统：

```bash
cd D:/code/blog
git push origin main --force
```

原来的代码仍然保留在 `D:/code/blog` 目录中。
