# sleep
# QQ 机器人项目打包说明

这个总文件夹包含两部分：

## 1. `github-source`

这是适合上传到 GitHub 的版本，包含：

- `NoneBot2` 机器人源码
- AI 聊天插件
- 画图插件
- `README.md`
- `.env.example`
- `requirements.txt`

这个目录**不包含**：

- 真实 API Key
- 真实 WebUI token
- 真实 QQ 号
- 本地 `.env`
- 虚拟环境
- 运行缓存
- 生成图片

## 2. `napcat-shell-template`

这是本项目运行时配套使用的 `NapCat Shell` 结构模板，包含：

- 启动脚本
- 必要目录结构
- 脱敏后的配置模板
- 运行说明

这个目录**不包含**：

- 二维码缓存
- 日志
- 真实 token
- 账号绑定配置
- 本地 passkey

## 3. 未打包的部分

以下内容不建议上传到 GitHub，也没有放进模板包：

- `QQNT` 客户端安装目录
- 真实 `.env`
- 本机账号数据目录

原因：

- `QQNT` 属于单独的客户端程序，体积大且不适合作为项目源码仓库的一部分
- 真实 `.env` 和 token 会泄露个人信息与密钥

## 4. 推荐上传方式

上传 GitHub 时，建议只上传：

- `github-source`

本地运行参考时，再结合：

- `napcat-shell-template`

## 5. 每次启动顺序

1. 先启动 `github-source` 里的机器人服务
2. 再启动 `NapCat Shell`
3. 确认 NapCat WebSocket 反向连接成功
4. 然后在 QQ 里测试聊天和画图
