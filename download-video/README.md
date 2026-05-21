# download-video-skill

A Claude Code skill that downloads videos by pasting a URL — powered by [yt-dlp](https://github.com/yt-dlp/yt-dlp).

## What it does

Once installed, just tell Claude "帮我下载这个视频" or paste a video link — Claude will run yt-dlp automatically and save the file to `~/Downloads`.

## Supported platforms

小红书 · 抖音 · YouTube · B站 · 快手 · Twitter/X · and [700+ more sites](https://github.com/yt-dlp/yt-dlp/blob/master/supportedsites.md)

## Requirements

Install yt-dlp via Homebrew:

```bash
brew install yt-dlp
```

## Installation

1. Download `SKILL.md` from this repo
2. Place it in `~/.claude/skills/download-video/SKILL.md`
3. Restart Claude Code

## Usage

Just paste a video URL and say:

> 帮我下载这个视频

Or use the slash command:

> /下载视频

## Disclaimer

For personal and educational use only. Please respect copyright laws and the terms of service of each platform.
