---
name: download-video
description: 用 yt-dlp 下载视频。当用户说"帮我下载"、"下载这个视频"、"下载这个链接"、贴出视频链接（小红书、抖音、YouTube、B站、快手、Twitter 等），或使用 /下载视频、/download-video 时触发。
---

# download-video

用 yt-dlp 下载用户提供的视频链接，默认保存到 ~/Downloads。

## 用法

```bash
cd ~/Downloads && yt-dlp "<URL>"
```

## 注意

- 直接用用户给的原始链接，不要修改
- 如果下载失败报错，把错误信息告诉用户
- 公开内容无需登录；若遇到需要登录的内容，告知用户需要提供 cookie
