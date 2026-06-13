# 今天我被优化了 · Optimized Away

纯 HTML5 单文件网页小游戏（Canvas 2D，零依赖）。打开网页就能玩，传到任何静态空间发个链接就能分享给别人。

> 玩法：你是一名打工人，头顶不断掉下各种「职场掉落物」。接住 💰 工资、☕ 咖啡、🎉 上线续命加血；躲开 📋 N+1 大礼包、⏰ 强制加班、🎂 35 岁危机扣血。血条（职场存活值）归零就被优化。活得越久，**在职天数**越高 —— 撑住，别下班。

## 怎么玩

- 最简单：**双击 `index.html`** —— 单文件零依赖，浏览器直接打开就能玩。
- 或本地起个服务（手机连同一 WiFi 也能扫着玩）：
  ```powershell
  python -m http.server 8092
  # 浏览器打开 http://localhost:8092/
  ```
- 操作：`← →` 方向键 / `A` `D` / 拖动 / 点屏幕左右半边移动托盘；`空格` / `回车` / 点击 = 开始或再就业。

## 放到网上（都免费）

任选其一，上传后得到一个公开链接，发给谁都能点开玩：

- **GitHub Pages**：本目录推到仓库 → Settings → Pages → 选分支 → 得到 `https://<用户名>.github.io/<仓库>/`
- **itch.io**：把 `index.html` 打包成 zip 上传，Kind 选 HTML，勾选 "This file will be played in the browser"
- **Netlify Drop**：打开 app.netlify.com/drop，直接把文件夹拖进去
- **Vercel / Cloudflare Pages**：连仓库或拖拽部署

## 技术说明

- 单文件 `index.html`，HTML + CSS + JS 全部内联，**无外部依赖、无构建步骤**。
- 画布全屏自适应；同时支持鼠标 / 触摸 / 键盘三种操作。
- 最高纪录（在职天数）用 `localStorage` 本地持久化。
- 全部玩法在一个 `Game` 类里：状态机（ready / playing / over）+ 掉落物生成 + 托盘接物碰撞判定 + 难度随时间递增（下落变快、坏物变多）+ 受击抖动 + 结算黑色幽默评语。

## 后续可做

- [ ] 把碰撞 / 加血扣血逻辑抽成纯函数 + 单测（日后换皮量产不回归）
- [ ] 分享：生成带「在职 N 天」的成绩图 / 一键复制
- [ ] 变现：接 GameDistribution / GameMonetize 的 H5 广告 SDK
- [ ] 换皮量产：改配色 + 文案 + 个别参数即可衍生新主题
- [ ] 音效：接物 / 受击 / 被优化的反馈音

## License

MIT，见 [LICENSE](LICENSE)。
