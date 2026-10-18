# Vibe Video

**给一个主题，制作一条无旁白知识动画。**

An agent skill for researched, beat-synced knowledge videos: Chinese on-screen storytelling, code animation, and a vertical 2K MP4. Model-independent instructions with local Python / Node.js / FFmpeg helpers.

默认成片：60 秒 · 1440×2560 · 30fps · H.264 / AAC · 无旁白。前 3 秒设计视觉钩子，使用深黑、冰蓝、香槟金、线框与粒子，通过画面和短文字解释概念。新主题会重新创作分镜与动画，不只是替换标题。

## 安装

通过 [skills CLI](https://skills.sh/docs/cli) 安装，按提示选择宿主：

```sh
npx skills add immurray/vibe-video --skill vibe-video
```

Hermes 也可以直接安装 GitHub 技能：

```sh
hermes skills install immurray/vibe-video/skills/vibe-video
```

或先添加自定义源：`hermes skills tap add immurray/vibe-video`。

手动安装：复制完整的 `skills/vibe-video/` 文件夹到 `~/.agents/skills/vibe-video`（Codex / DSH 共享发现）、`~/.dsh/skills/vibe-video` 或 `~/.hermes/skills/vibe-video`。不要只复制 SKILL.md。详见 [宿主兼容说明](skills/vibe-video/references/compatibility.md)。

## 首次配置

需要一个能读写文件、执行命令、联网核查和查看图片的代理环境；普通纯聊天页面不能完成本地渲染。

1. 安装 Python 3.9+、Node.js 20+、FFmpeg / FFprobe 和中文字体。
2. 从技能的 `assets/requirements.txt` 安装 Python 包，项目的 `package.json` 安装 Node 依赖；运行 `scripts/doctor.py --project <项目目录>` 检查。详细步骤见 [渲染说明](skills/vibe-video/references/rendering.md)。
3. 将 `assets/local-profile.example.json` 复制到技能目录的 `local-profile.json`，填入本地配乐路径。也可设置 `VIBE_MUSIC` 或使用 `prepare.py --music`。私人配置不要提交到 Git。

完成一次环境与配乐配置后，以后只需给主题：

```text
Codex:  $vibe-video 主题：如果光速突然变慢
Hermes: /vibe-video 主题：如果光速突然变慢
DSH:    使用 vibe-video，主题：如果光速突然变慢
```

用户指定的时长、语言、配乐和风格优先于默认设置。输出 MP4、技术验收报告及参考来源；技能不会自动发布视频、创建定时任务或购买素材。

## 工作方式

事实核查 → 叙事分镜 → 真实音频事件分析 → 代码动画 → 关键帧审片 → 混音导出 → 全片解码与规格检查。科学事实、假说、类比与科幻设定必须区分。

内附《二向箔》原创代码案例，以及 `prepare.py`、`analyze_music.py`、`doctor.py`、`finish.py`。代码可复用，主题内容需要模型重新创作。无内置模型 SDK、API Key 或供应商账号；模型由宿主选择。

## 验证范围

macOS 辅助脚本、中文关键帧、原生 2K / 30fps 短片渲染和全片解码已测试；原案例完成过 60 秒成片。skills CLI 与 Hermes 已从公开 GitHub 仓库成功安装完整技能；Hermes 安装扫描结果为 SAFE。DSH、不同模型的新主题端到端出片，以及 Linux / Windows 完整渲染尚未验证。格式兼容不保证模型质量一致。详见 [VALIDATION.md](VALIDATION.md)。

## 许可与分发

[MIT](LICENSE)，发布者 [immurray](https://github.com/immurray)。公共包不含歌曲、视频、商业字体、个人路径或凭据。使用者自行提供适用的音乐与字体；代码许可不授予第三方素材权利。

GitHub 是公开分发源；skills.sh 收录、Hermes 官方推荐和 OpenAI 目录审核是各自独立的状态。见 [PUBLISHING.md](PUBLISHING.md)。问题请提交到 [Issues](https://github.com/immurray/vibe-video/issues)。
