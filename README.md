# codeapp

这是一个 **moltbot 助手** 的测试项目（Cloudflare Pages 静态站点）。

用途：
- 验证部署流程：本地修改 → git 提交 → Cloudflare Pages 部署
- 放一些小 Demo 页面（例如行情展示页）
- 作为 moltbot 的线上测试入口

## 页面

- `/`：漂亮的 Hello World（测试首页）
- `/sol.html`：SOL → USDT 实时价格（使用 Binance 公共接口，支持跨域、无需授权）

## 本地运行

直接打开 `index.html` 也能看；推荐用本地静态服务器：

```bash
python3 -m http.server 8000
# 然后访问 http://localhost:8000
```

## 部署（Cloudflare Pages）

在服务器项目目录执行：

```bash
cd /www/bear/projects/codeapp
# 如果你使用了 direnv：
direnv exec . wrangler pages deploy . --project-name codeapp --commit-dirty=true
```

> 说明：本项目会使用 `.envrc` 存放 Cloudflare Token 等环境变量，该文件已加入 `.gitignore`，不要提交到 GitHub。
