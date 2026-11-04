# Life手帐（GitHub 手机网页上传简化版）

## 上传步骤
在解压后的文件夹中，把以下 5 个文件上传到 GitHub 仓库根目录：
- index.html
- manifest.webmanifest
- sw.js
- icon.svg
- README.md

不要上传 ZIP 文件本身。所有文件都放在仓库根目录，不需要手动创建文件夹。

## 免费部署
在 Cloudflare Pages 中连接 GitHub 仓库，Framework preset 选择 None，Build command 留空，Build output directory 填 `.`。

## 重要说明
这是方便先免费发布的静态版。日记、计划等前端功能主要保存在当前浏览器。此版不包含后端 API 文件，因此 AI 服务端接口、账号同步和真实支付未启用；7 天试用与 ¥18/月仅为界面演示。正式收费前需要配置后端、数据库、身份验证、AI 密钥和支付验证。


## 2.1 维护更新
- 增加 JSON 备份导入，支持从之前导出的备份恢复数据。
- 备份导出文件名包含本地日期。
- 日期键改为设备本地日期，避免跨时区时日记/心情归档到前一天。
- 增加本地存储写入失败提示。
- 更新 Service Worker 缓存版本，避免旧页面缓存影响更新。
- 保留原有 localStorage 数据键 `life-journal_v2_data`，升级不会主动清空旧数据。
