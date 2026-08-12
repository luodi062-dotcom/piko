# 片羽 Piko · 产品介绍网站

Piko/片羽 是一款安卓相册清理 App 的官方介绍站点（纯静态，无需后端）。

## 目录结构

```
piko-website/
├── index.html              # 主页面（功能介绍 / 下载 / 开发者 / 反馈通道）
├── assets/
│   ├── logo.png            # App logo（导航 / Hero / 页脚）
│   └── avatar.jpg          # 开发者头像（罗笛）
├── downloads/
│   └── piko-v1.11.apk      # 最新安装包（v1.11）
└── .github/workflows/pages.yml   # GitHub Pages 自动部署工作流
```

## 本地预览

直接用浏览器打开 `index.html` 即可；或起一个本地静态服务器：

```bash
python3 -m http.server 3000
# 浏览器访问 http://localhost:3000
```

## 部署到 GitHub Pages（上线步骤）

1. 在 GitHub 新建一个**空仓库**（例如 `piko-site`），不要勾选 README/LICENSE。
2. 在本目录执行（把 `<你的用户名>/<仓库名>` 换成实际值）：

   ```bash
   git init
   git add .
   git commit -m "init piko website"
   git branch -M main
   git remote add origin https://github.com/<你的用户名>/<仓库名>.git
   git push -u origin main
   ```

3. 推送后进入仓库 **Settings → Pages**：
   - Source 选择 **GitHub Actions**（工作流已内置，无需手动选分支）。
4. 等待 1~2 分钟，Actions 跑完，站点地址为：
   `https://<你的用户名>.github.io/<仓库名>/`

> 以后每次改完页面，`git add . && git commit && git push` 即可自动重新部署。

## 自定义域名（可选，后续要做时）

在仓库 **Settings → Pages → Custom domain** 填入你的域名，并按提示在域名 DNS 加一条 CNAME 记录指向
`<你的用户名>.github.io`。本站点已设置 `base` 相对路径，迁移域名无需改代码。
