Life手帐 2.2.0 云同步部署说明

1. 打开 index.html，搜索 SUPABASE_PUBLISHABLE_KEY。
2. 将 PASTE_YOUR_SB_PUBLISHABLE_KEY_HERE 替换为你自己的 Supabase Publishable Key。
3. 不要使用 service_role / Secret Key，也不要把密钥发给任何人。
4. Supabase 表 user_data 应包含 user_id（uuid，唯一）、data（jsonb）、updated_at（timestamptz）。
5. 开启 RLS，并创建仅允许 authenticated 用户读写自己 user_id 的策略。
6. 上传 index.html、sw.js、manifest.webmanifest、icon.svg 到 GitHub main 根目录。
7. 等待 Cloudflare Pages Production 成功，再用无痕窗口或清除站点缓存验证版本。

提示：AI 与会员支付尚未接入真实服务端，不会发生真实扣款。
