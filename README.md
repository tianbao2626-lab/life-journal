# Life手帐 Life Journal — 2.1 升级版

## 本版更新
- 修正页面版本标识为 2.1。
- 更新 Service Worker 缓存版本，帮助手机浏览器加载新页面。
- 保留原有本地数据键 `life-journal_v2_data`，不会主动清除旧记录。
- 支持导出 JSON 备份、导入 JSON 备份；导入前会提示确认。
- 使用设备本地日期归档日记、心情和灵感，减少跨时区日期偏差。
- 试用结束后不再自动弹出付费遮罩，也不会锁住已有本地记录。

## 安卓手机上传 GitHub
1. 解压 ZIP。进入 `life-journal-main` 文件夹。
2. 打开 GitHub 仓库的根目录（不要进入其他子文件夹）。
3. 上传并覆盖同名文件：`index.html`、`sw.js`、`manifest.webmanifest`、`icon.svg`、`README.md`。
4. 提交更改（Commit changes）。
5. 打开 Cloudflare Pages → 项目 → Deployments，等待最新部署显示 Success。
6. 用 Chrome 打开网站，刷新；如仍显示旧版，关闭网站标签页后重新打开，或清除该站点缓存。

## Cloudflare Pages 设置
如果已连接 GitHub 自动部署，无需重新创建项目。Framework preset: None；Build command 留空；Build output directory: `.`。

## 重要说明
这是可免费部署的静态网页应用。日记、待办、计划、习惯和设置保存在当前浏览器的 localStorage 中；不会自动跨设备同步。请定期导出 JSON 备份。

AI 页面提供本地模板演示；正式 AI 生成需要配置安全的服务端 API。18 元/月仅为方案展示；本包没有真实支付、账号系统或服务端会员验证，不会扣款，也不应对外宣称已具备正式收费能力。
