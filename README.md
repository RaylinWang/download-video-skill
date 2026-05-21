# raylinskill

一些自用的 Claude Code skill，顺手公开。

## 当前包含

| Skill | 一句话说明 | 触发词 |
|---|---|---|
| [download-video](./download-video) | 用 yt-dlp 下载视频（小红书 / 抖音 / YouTube / B站 / 快手 / Twitter 等） | `/下载视频`、`/download-video`、贴链接 |
| [video-to-text](./video-to-text) | 本地视频转中文文字报告：`mlx_whisper` 转录 + 语义分段 + 双人角色推断 + 核心观点总结 | `/视频转文字`、`/video-to-text` |

## 安装

skill 平铺在仓库根目录，每个目录是一个独立 skill。挑你想要的拷到 Claude Code 的 skills 目录即可：

```bash
git clone https://github.com/RaylinWang/raylinskill.git
cp -r raylinskill/download-video ~/.claude/skills/
cp -r raylinskill/video-to-text  ~/.claude/skills/
```

或者只拿一个：

```bash
git clone --depth 1 --filter=blob:none --sparse https://github.com/RaylinWang/raylinskill.git
cd raylinskill
git sparse-checkout set video-to-text
cp -r video-to-text ~/.claude/skills/
```

装完重启 Claude Code，输入 `/` 就能看到。

## 依赖

- **download-video**：`yt-dlp`
  ```bash
  brew install yt-dlp
  ```
- **video-to-text**：Whisper（MLX 版）+ `ffmpeg`
  ```bash
  uv tool install --python 3.12 mlx-whisper
  brew install ffmpeg
  ```

## 兼容性

- Claude Code（终端 CLI）
- macOS 为主；Linux 应该也能跑，未测
- video-to-text 依赖 MLX，仅 Apple Silicon

## License

MIT，随便用。改了告诉我一声更好，不告诉也行。
