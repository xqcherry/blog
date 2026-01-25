# 使用 Hugo + Vercel 搭建个人博客全流程指南

这是一份使用 **Hugo** 静态网站生成器和 **Vercel** 托管服务，快速搭建高性能、高自定义度个人博客的完整实战手册。

## 🌟 成果预览

在开始之前，你可以先看看搭建完成后的样子：

> **[🌐 我的个人博客：[点击访问]](https://xqcherry-blog.vercel.app/)**
> *基于 Hugo 构建，由 Vercel 提供全球加速*

---

## 🛠️ 阶段一：本地环境搭建与内容准备

### 1. 安装必备工具

确保你的电脑已安装以下软件，并配置好环境变量：

* **Git**: 用于版本控制和代码同步。[👉 下载 Git](https://git-scm.com)
* **Node.js**: (可选) 某些高级主题（如需编译 TS/JS）可能需要。[👉 下载 Node.js](https://nodejs.org)
* **Hugo Extended 版本**: ⚠️ **必须使用 Extended 版本**，否则无法编译部分主题的 SCSS/SASS 样式。
* *安装建议*：下载后务必将 `hugo.exe` 所在的文件夹路径添加至系统的 **环境变量 (Path)** 中。



### 2. 创建博客项目骨架

打开命令行（如 PowerShell 或 Terminal），运行以下命令：

```bash
# 创建项目文件夹
hugo new site myblog
cd myblog

# 初始化 Git 仓库
git init
```

### 3. 选择并配置主题

1. 从 [Hugo Themes](https://themes.gohugo.io/) 选择一个心仪的主题（例如 `hugo-coder`）。
2. 将其克隆或移动到 `themes/` 目录下。
3. **(关键步骤)**：将主题文件夹内 `exampleSite` 目录下的配置文件（通常是 `config.toml` 或 `hugo.toml`）复制并覆盖到你博客根目录下的同名文件，这样运行时就能直接看到与 Demo 一致的效果。

### 4. 本地预览与魔改

在命令行运行以下命令，启动本地服务器：

```bash
hugo server
```

* **访问地址**：`http://localhost:1313`
* **操作建议**：此时可以使用 VS Code 修改 `hugo.toml` 配置和 `content/` 文件夹下的示例文章，浏览器会自动刷新预览。

---

## 🌐 阶段二：上线部署到 Vercel

### 1. 关联 GitHub 仓库

1. 在 GitHub 上创建一个新的公开仓库（例如 `my-hugo-site`）。
2. 回到本地命令行，将代码推送到远程仓库：

```bash
git add .
git commit -m "Initial Hugo setup"
git branch -M main
git remote add origin https://github.com/你的用户名/仓库名.git
git push -u origin main
```

### 2. 使用 Vercel 自动化部署

1. 登录 [Vercel](https://vercel.com/)，点击 **Add New Project**。
2. 导入你刚才创建的 GitHub 仓库。
3. **框架识别**：Vercel 会自动识别 Framework 为 **Hugo**。
4. 点击 **Deploy**，等待进度条完成后即可上线。

### 3. 访问你的博客

部署成功后，Vercel 会分配一个以 `.vercel.app` 结尾的免费二级域名，全球用户均可访问。

---

## ⚡ 阶段三：后续维护与管理

* **发布文章**：在本地 `content/posts/` 创建 `.md` 文件，编辑后执行 `git push`。Vercel 监听到变动后会自动触发构建。
* **绑定域名**：在 Vercel 项目设置的 `Settings -> Domains` 中添加你购买的域名，并根据提示修改 DNS 记录。
* **深度定制**：修改 `assets/` 下的 CSS 或主题模版，打造独一无二的视觉效果。

---

## 🤝 交流与反馈

感谢阅读。如果这份指南对你有所帮助，欢迎访问我的 **[个人博客](https://xqcherry-blog.vercel.app/)** 查看更多技术分享。

你也可以在 [GitHub](https://github.com/xqcherry) 上关注我的其它开源项目。若搭建过程中有任何疑问，欢迎在博客留言板交流探讨