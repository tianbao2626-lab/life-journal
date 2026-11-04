Life手帐 2.2 云同步升级版

本版本在 2.1 基础上增加：
- Supabase 邮箱注册、登录、退出登录
- 使用 public.user_data 保存每个账号的 JSON 手帐数据
- 登录时读取云端；云端无数据时首次上传本设备数据
- 本地保存后延迟约 1.2 秒自动同步；也可手动点击“立即同步”
- 保留原有日记、待办、计划、习惯、本地备份导入/导出和中英文界面

部署前必须完成一次配置：
1. 解压 ZIP，打开 life-journal-main/index.html。
2. 搜索：PASTE_YOUR_SB_PUBLISHABLE_KEY_HERE
3. 将它替换为你在 Supabase 项目 Settings -> API Keys 中复制的 sb_publishable_ 开头的 Publishable Key。
4. 不要粘贴 sb_secret_、service_role 或数据库密码。
5. 保存 index.html，然后将 life-journal-main 文件夹内的全部文件上传到 Cloudflare Pages，覆盖旧版本。

已预填项目 URL：
https://bdrlyluynxslblkvqfci.supabase.co

Supabase 需要已经完成：
- Authentication -> Sign In / Providers -> Email 已启用
- Authentication -> URL Configuration
  Site URL: https://life-journal-9rz.pages.dev
  Redirect URL: https://life-journal-9rz.pages.dev/**
- SQL Editor 已执行 user_data 表及 RLS 策略创建语句

首次使用建议：
1. 先在当前设备导出 JSON 备份。
2. 打开部署后的网站，进入“试用与会员”->“账号与云同步”。
3. 注册邮箱，检查收件箱并点击 Supabase 验证邮件。
4. 返回网站，用已验证邮箱登录。
5. 若该账号云端尚无数据，会首次上传当前设备数据；若云端已有数据，则云端数据会载入并覆盖当前页面内存及本地存储。请在登录前做好本地备份。
6. 在另一台设备登录同一账号，检查记录是否出现。

重要限制：
- 这是前端 Supabase Auth + RLS 数据同步接入版本。请确保 user_data 表已启用 RLS，且仅有 auth.uid() = user_id 的策略。
- 本版本尚未接入真实 AI 服务，也未接入真实支付；会员按钮不会扣款。不要将当前版本当作已完成商业化上线版本。
- Publishable Key 可放在前端，但任何 Secret / service_role key 都不得放入前端、ZIP 或 GitHub。
- 当前采用整份 JSON 同步，适合早期个人数据量；未来规模化前应增加冲突处理、版本控制、删除同步、隐私政策和服务端会员权限。
- 依赖 jsDelivr 加载 Supabase JS v2，首次打开需要网络连接。
