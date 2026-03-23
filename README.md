# statphys-notes

这是一个使用 https://quartz.jzhao.xyz/ 构建的个人笔记与数字花园项目，托管于 GitHub Pages。  
在线访问地址：**https://ttt125145.github.io/statphys-notes/**

---

## 📦 环境准备

在开始之前，请确保你的本地环境满足以下要求：

- **Node.js**：v22 或以上  
- **npm**：v10.9.2 或以上  
- **Git**：已安装并可正常使用  

你可以在终端中运行以下命令检查版本：

```bash
node -v
npm -v
git -v
```

---

## 🚀 克隆项目

如果你尚未将项目克隆到本地，请执行：

```bash
git clone https://github.com/ttt125145/statphys-notes.git
cd statphys-notes
npm install
```

> 说明：该项目是基于 Quartz 官方模板初始化的，已包含必要的配置文件与 GitHub Actions 部署脚本。

---

## ✍️ 编辑笔记内容

所有笔记内容均存放在 `content` 目录中，使用 Markdown 编写。

### 基本流程

1. 在项目根目录下，进入 `content` 文件夹：
   ```bash
   cd content
   ```

2. 新建或修改 `.md` 文件，例如：
   ```text
   content/
   ├── index.md
   ├── physics/
   │   └── thermodynamics.md
   └── math/
       └── linear-algebra.md
   ```

3. 支持 Quartz 提供的全部功能，包括但不限于：
   - Wikilinks（`[[文件名]]`）
   - 数学公式（LaTeX）
   - 代码块语法高亮
   - 反向链接与图谱视图

---

## 👀 本地预览

在提交更改前，建议先在本地预览效果：

```bash
npx quartz build --serve
```

随后在浏览器中打开：

```
http://localhost:8080
```

该命令会监听文件变化并增量重建，适合写作阶段使用。

---

## 🔄 更新与发布网站

当你完成笔记修改并准备发布时，只需执行一条命令：

```bash
npx quartz sync
```

或更明确地（跳过拉取远程更新）：

```bash
npx quartz sync --no-pull
```

### 这条命令会做什么？

1. 自动将你的更改加入 Git（`git add`）
2. 创建提交（`git commit`）
3. 推送到你的远程仓库 `origin`（即 `ttt125145/statphys-notes`）

### 自动部署机制

- 项目根目录中包含 `.github/workflows/deploy.yml`
- 当你将代码推送到指定分支（如 `v4`）后：
  - GitHub Actions 会自动执行 `npx quartz build`
  - 构建产物（`public` 目录）会被部署到 GitHub Pages

### 页面更新时间

- 通常需要 **1–5 分钟**
- 若长时间未更新，可前往 GitHub 仓库的 **Actions** 页面查看工作流状态

---

## ✅ 日常维护流程总结

```text
编辑 content 中的 Markdown 文件
        ↓
npx quartz build --serve（本地预览，可选）
        ↓
npx quartz sync（或 npx quartz sync --no-pull）
        ↓
等待 GitHub Actions 自动构建与部署
        ↓
访问 https://ttt125145.github.io/statphys-notes/
```

---

## ❓ 常见问题

**Q：我需要手动推送 `public` 目录吗？**  
A：不需要。`public` 目录是构建产物，由 GitHub Actions 自动生成并部署，你只需推送源码。

**Q：为什么页面没有立即更新？**  
A：可能是 GitHub Actions 仍在运行，或构建失败。请在仓库的 **Actions** 页面查看日志。

**Q：我可以只写笔记而不关心配置吗？**  
A：可以。只要你不修改 `quartz.config.ts` 或布局文件，日常只需维护 `content` 目录即可。

---

如需进一步自定义 Quartz 的行为或外观，可参考：
- https://quartz.jzhao.xyz/
- 本项目中的 `quartz.config.ts` 与 `layouts` 目录


# Quartz v4

> “[One] who works with the door open gets all kinds of interruptions, but [they] also occasionally gets clues as to what the world is and what might be important.” — Richard Hamming

Quartz is a set of tools that helps you publish your [digital garden](https://jzhao.xyz/posts/networked-thought) and notes as a website for free.

🔗 Read the documentation and get started: https://quartz.jzhao.xyz/

[Join the Discord Community](https://discord.gg/cRFFHYye7t)

## Sponsors

<p align="center">
  <a href="https://github.com/sponsors/jackyzha0">
    <img src="https://cdn.jsdelivr.net/gh/jackyzha0/jackyzha0/sponsorkit/sponsors.svg" />
  </a>
</p>
