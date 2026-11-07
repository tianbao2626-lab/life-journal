# Life手帐 Life Journal 2.2.0

这是基于你之前的 Life手帐项目整理的 2.2.0 部署包。

## 上传前必须完成：Supabase Publishable Key
1. 用文本编辑器打开 `index.html`。
2. 搜索 `SUPABASE_PUBLISHABLE_KEY`。
3. 将 `PASTE_YOUR_SB_PUBLISHABLE_KEY_HERE` 替换成你在 Supabase 项目设置中复制的 **Publishable Key**。
4. 只使用 Publishable/anon 公钥，不要使用 `service_role` 或 Secret Key。
5. 保存文件。

Supabase URL 已保留为你之前提供的项目地址：
`https://bdrlyluynxslblkvqfci.supabase.co`

## GitHub 上传
将 `index.html`、`sw.js`、`manifest.webmanifest`、`icon.svg` 上传到仓库 `main` 分支的根目录并覆盖同名文件。README 文件可选上传。
上传后等待 Cloudflare Pages 的 Production 部署完成。

## 重要说明
- 这是 2.2.0 客户端部署测试版，不代表 AI 或会员支付已接通。
- AI 页面当前包含本地模板回退；真正 AI 需要安全的服务端 `/api/ai`。
- 会员按钮需要服务端 `/api/checkout` 和真实支付/会员状态校验；当前不会真实扣款。
- 云同步需要 Supabase `user_data` 表、以 `user_id` 为唯一键，并配置正确的 RLS 策略，限制用户只能访问自己的记录。
- 上传前请先在旧版导出 JSON 备份。首次登录云同步时，遵循页面提示检查云端与本地数据。
