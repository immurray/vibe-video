# 分发渠道

版本 1.1.0；发布账号 immurray；公开源码与说明采用 MIT。

## GitHub

源仓库：https://github.com/immurray/vibe-video

版本与下载：https://github.com/immurray/vibe-video/releases

核心技能位于 `skills/vibe-video/`；插件压缩包根目录包含 `plugin.json`。

## skills.sh

安装命令：`npx skills add immurray/vibe-video --skill vibe-video`。

skills.sh 使用 GitHub 技能和安装遥测进行收录与排名，没有单独上传 ZIP 的上架步骤。公开可安装不代表已经进入榜单；网站索引需要单独确认。

官方说明：https://skills.sh/docs/faq

## Hermes Skills Hub

直接安装：`hermes skills install immurray/vibe-video/skills/vibe-video`。

自定义源：`hermes skills tap add immurray/vibe-video`。

GitHub tap 可供用户添加和安装；它不等于 Hermes 官方推荐。

官方说明：https://hermes-agent.nousresearch.com/docs/user-guide/features/skills/#publishing-a-custom-skill-tap

## OpenAI 插件目录

提供 skills-only 插件包。清单已包含 MIT 许可、发布者、展示文字、图标、支持链接与 `extensions.com.openai.requires_local_executor=true`。依赖本地 FFmpeg 和文件执行；不包含 MCP server。

平台上传、自动检查、审核和最终发布仍是独立步骤。本文件不代表已获 OpenAI 审核或上架；以平台实际回执为准。

提交入口：https://platform.openai.com/plugins

官方说明：https://developers.openai.com/plugins/deploy/submission

## 发布内容边界

公共包不分发《千年之后（氛围版）》录音或字体。私人配乐配置、源媒体、生成视频与缓存不纳入公共仓库。使用者自行提供音乐与字体。
