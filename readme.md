# Checkin

GitHub Actions 实现 [GLaDOS][glados] 自动签到

([GLaDOS][glados] 可用邀请码: `D06PQ-QU3XK-53AAL-2RRDO`, 双方都有奖励天数)

## 使用说明

1. Fork 这个仓库, 点击 Create fork 创建你的副本, 等待一下, 完成后会自动跳转

1. 登录 [GLaDOS][glados] 获取 Cookie
   1. 打开浏览器「开发者工具」(快捷键 F12 或 Ctrl+Shift+I), 切换到「网络 Network」标签页
   1. 找到名字为 status 这一行, 点击打开详情, 在「请求头 Request」找到 Cookie, 格式类似 koa:sess=xxxxxx; koa:sess.sig=xxxxxx, 复制出来备用

1. 添加 Cookie 到 Secret `GLADOS`
    1. 打开 GitHub 仓库设置 Settings → Secrets and variables → Actions → New repository secret, 按照提示填写完成后保存
        1. Name: GLADOS
        1. Secret: 前面获取的 GLaDOS Cookie 值

1. 启用 Actions, 每天北京时间 00:10 自动签到
   1. 打开 GitHub 仓库 Actions 标签页, 点击 I understand my workflows, go ahead and enable them

1. 如需推送通知, 可用 [PushPlus][pushplus], 添加 Token 到 Secret `NOTIFY`
   1. 打开 PushPlus, 微信扫码登录
   1. 登录后会显示一个 Token, 复制出来
   1. 转到 GitHub 打开仓库设置 Settings → Secrets and variables → Actions → New repository secret, 填写完成后保存
      1. Name: NOTIFY
      1. Secret: 前面获取的 Token 值

[glados]: https://github.com/glados-network/GLaDOS
[pushplus]: https://www.pushplus.plus/
