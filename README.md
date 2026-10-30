# 云上仙宫视觉与视频工作流Skill

`roths-cloud-palace-mj` 是一个用于创作“云上仙宫／天宫巨物美学”的 Agent Skill，能够把东方空间秩序、超大尺度建筑、云海自然奇观和神兽礼器，转译成 Midjourney 英文提示词与图生视频动态提示词。Codex、Claude Code、Cursor、CodeBuddy 等 70+ 支持 Skill 的 Agent 都能直接用。

## 这个 Skill 能做什么

- 从 A–J 十个视觉方向中选择云上仙宫构图。
- 生成或修订 Midjourney 英文生图提示词。
- 根据定稿图设计图生视频动态提示词。
- 规划镜头排序、封面和发布文案。
- 处理巨门、瀑墙、月门、星球天城、神兽、冰雪神城和地质圣谷等视觉母题。

这个 Skill 不会直接调用 Midjourney，主要负责生成符合云上仙宫视觉规则的 MJ 英文提示词。

## 十个云上仙宫方向

| 方向 | 简要说明 |
|---|---|
| A｜云海礼制天门 | 以巨门、长阶、高台和门—阶—殿秩序构成天界礼制入口，强调庄严、尺度与朝圣路径。 |
| B｜悬空仙宫与峭壁飞瀑 | 让仙宫、峭壁与瀑布彼此转化，建筑可以成为瀑墙、从岩层生长或跨越峡谷。 |
| C｜洞天月门与松树框景 | 用圆门、白墙、古松和留白组织可进入的东方画卷，依靠少量大色块和框景成立。 |
| D｜云海行廊与边界秩序 | 沿天界边缘展开无限长廊、宫墙和悬挑平台，以侧向消失、重复柱列与云海留白制造秩序感。 |
| E｜星球天城与宇宙神域 | 将东方天宫提升为宇宙尺度文明，用行星弧面、天外回廊和极小人物表现宏大的神域边界。 |
| F｜神兽、礼器与仪式奇观 | 让真实神兽、神祇或巨钟、神树等礼器成为显圣、守护或祭仪高潮。 |
| G｜大地天阙与俯瞰天城 | 从高处揭示统摄山河的世界级天城，使用前景崖顶、中景大地和远景天城建立世界尺度。 |
| H｜草原巨门与山体建筑 | 让平坦草原连续向上折起形成近垂直山墙，巨门或深檐像从同一片大地中生长出来。 |
| I｜冰雪神城与裂谷防线 | 以雪原、冰墙、长城、裂谷和塔门构成寒冷边境，强调守界、危险与冷峻气质。 |
| J｜地质巨壁与原初圣谷 | 弱化或取消建筑，让褶皱岩壁、环谷、深洞和沉积层理成为自然形成的原初神殿。 |

## 如何安装

一条命令，不需要下载 ZIP，也不用改任何路径：

```bash
npx skills add Roths-yang/roths-cloud-palace-mj -g
```

运行后按提示选择目标 Agent 即可——skills CLI 支持 Codex、Claude Code、Cursor、CodeBuddy 等 70+ 通用 Agent，技能会装进所选 Agent 的用户级 skills 目录，所有项目都能调用。需要 Node.js 22.20 或更高版本，Windows / macOS / Linux 通用。

### 交给 AI Agent 安装

把这句话发给任意 AI Agent：

```text
帮我安装 roths-cloud-palace-mj 技能。执行 npx skills add Roths-yang/roths-cloud-palace-mj -g，装完后检查 roths-cloud-palace-mj 目录下的 SKILL.md 和 references/ 是否存在。
```

### 更新与卸载

```bash
npx skills update roths-cloud-palace-mj -g -y   # 更新到最新版本
npx skills remove roths-cloud-palace-mj -g -y   # 卸载
```

### 离线安装（没有 Node 环境时）

1. 从 [GitHub Releases](https://github.com/Roths-yang/roths-cloud-palace-mj/releases) 下载 `roths-cloud-palace-mj-v2.zip`；
2. 解压后把 `roths-cloud-palace-mj` 文件夹整个放进所用 Agent 的用户级 skills 目录（Codex 为 `~/.agents/skills/`，Claude Code 为 `~/.claude/skills/`）；
3. 重启 Agent，能在技能列表里看到 `roths-cloud-palace-mj` 即安装成功。

## 安装后如何调用

在新的 Agent 对话中输入：

```text
请使用 roths-cloud-palace-mj Skill，选择 B 方向：巨大的米白色仙界城墙悬浮在云海之上，瀑布从城墙倾泻，一个极小的白衣仙人立在远处。生成 2 版 Midjourney 英文提示词。
```

也可以直接指定其他方向，例如：

```text
请使用 roths-cloud-palace-mj Skill，选择 H 方向，生成一条表现“草原连续折起形成巨大山墙，仙门从山体中生长出来”的 Midjourney 英文提示词。
```

## 技能目录结构

技能装进 Skills 目录（如 `~/.agents/skills/`）后，结构如下：

```text
roths-cloud-palace-mj/
├── SKILL.md
├── README.md
├── evals/
│   └── evals.json
└── references/
    ├── directions.md
    ├── edit-release.md
    ├── failure-fixes.md
    ├── video-motion.md
    ├── visual-language.md
    └── workflow.md
```

| 文件或目录 | 用途 |
|---|---|
| [`SKILL.md`](SKILL.md) | Skill 主入口，包含视觉规则、A–J 方向、提示词格式、工作流和终检清单。 |
| [`README.md`](README.md) | 说明文档，介绍 Skill 能力、十个方向对照、安装与调用方法、目录结构。 |
| [`evals/evals.json`](evals/evals.json) | Skill 评测用例，覆盖方向识别、巨物尺度、神兽、地貌联想、图生视频和剪辑包装。 |
| [`references/directions.md`](references/directions.md) | 十个云上仙宫方向的详细说明，包括母题、大形、构图、色材和常见误区。 |
| [`references/edit-release.md`](references/edit-release.md) | 镜头排序、封面选择和发布文案的判断方法。 |
| [`references/failure-fixes.md`](references/failure-fixes.md) | 建筑太小、人物过大、地貌字面化、草原山体断裂等常见问题的修正方法。 |
| [`references/video-motion.md`](references/video-motion.md) | 图生视频动态提示词规则，包括主运镜、视差、人物动作和画面稳定性。 |
| [`references/visual-language.md`](references/visual-language.md) | 云上仙宫的世界观、构图、色彩、材质和“似而不直”的适用边界。 |
| [`references/workflow.md`](references/workflow.md) | 从定主题、写提示词、生成视频，到选片、剪辑和发布的完整工作流。 |

## 使用说明

- 方向可以单独使用，也可以借用其他方向的一项构图手法。
- 选择方向后，应保持该方向的核心母题和空间关系。
- 真实神兽可以完整、清晰地出现；“似而不直”主要用于自然地貌中的动物轮廓联想。
- 这个 Skill 不直接调用 Midjourney，也不会自动发布内容。