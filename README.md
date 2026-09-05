# ⚽ 足球战术板 —— PWA 部署包

这是单文件战术板的**可部署版本**（PWA：网页应用化 + 离线缓存），把整个文件夹传上任意 HTTPS 静态托管后，手机/电脑浏览器打开即可，还可“添加到主屏幕”像 App 一样用，且语音可用。

> 想保留电脑本地双击即用版？用根目录的 `football-tactics-board.html`（单文件，无需部署）。
> 本文件夹是给“手机上像 App 一样用 / 发给别人用”准备的。

## 文件夹内容

```
football-tactics-pwa/
├─ index.html            # 战术板（已加入 manifest / service worker）
├─ manifest.webmanifest  # 安装信息（名称、图标、全屏等）
├─ sw.js                 # 离线缓存
├─ icons/
│  ├─ icon-192.png       # 桌面图标（小）
│  └─ icon-512.png       # 桌面图标（大）
└─ README.md
```

## 一键部署（任选其一，都是免费的 HTTPS）

### 方式 A：GitHub Pages（推荐，有账号即可）
1. 到 https://github.com 新建一个仓库（公开即可），把 `football-tactics-pwa` 文件夹里**全部文件**上传（点仓库里 Upload files）。
2. 仓库 Settings → Pages → Source 选 `main` 分支根目录 → Save。
3. 等 1~2 分钟，得到网址 `https://<你的用户名>.github.io/<仓库名>/index.html`。

### 方式 B：Netlify Drop（最快，无需注册可先试）
1. 打开 https://app.netlify.com/drop
2. 把整个 `football-tactics-pwa` 文件夹拖进去 → 立刻得到一个 `https://xxx.netlify.app` 网址。

### 方式 C：Vercel
1. 打开 https://vercel.com/new → 上传项目 → 选择文件夹即可。

## 在手机上“装”起来（添加到主屏幕）

用手机浏览器（Chrome / Edge）打开上面的网址：
1. 右上角菜单（⋮）→ **“添加到主屏幕” / “安装应用”**；
2. 桌面出现 ⚽ 图标，点开即全屏运行，**离线也能开**（Service Worker 已缓存）；
3. 语音识别在 HTTPS 下可用（点「🎤 语音控制」，允许麦克风）。

## 注意
- 每次修改 `index.html` 后重新部署即可；浏览器里可能需刷新两次（或清站点数据）以更新缓存，因为离线缓存优先。
- 若更新了内容但手机还显示旧版：在页面里长按刷新 / 或 Chrome 设置 → 站点设置 → 清除数据后重进。
