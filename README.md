# Brand Event Pitch Skill

用于创建和打磨「品牌招商 / 赞助合作 / 联合营销活动」相关方案的 agent skill。

它适合这些任务：

- 生成品牌招商 PPT 的故事线和页序
- 生成招商方案 / 招商手册 / 飞书文档式方案
- 将已有招商 PPT 扩写成可阅读、可执行的招商方案文档
- 自动学习一个入口下的招商飞书文档、PPT、PDF 样本，并沉淀为可迁移规则
- 改写营销活动招商方案
- 审查招商 PPT 的商业逻辑、资源表达和页面顺序
- 将成熟故事线继续扩展成 HTML slides
- 使用内置公开风格预设和 `frontend-slides` 模板包生成视觉方向
- 生成图像先行、主题相关的招商视觉页，而不是纯文字报告
- 避免自动生成页眉署名、部门抬头、负责人姓名和邮箱

## 使用方式

### Codex

```bash
mkdir -p ~/.codex/skills
cp -R brand-event-pitch ~/.codex/skills/
```

然后在 Codex 里这样使用：

```text
用 $brand-event-pitch，帮我做一个营销活动品牌招商PPT。
活动是：夏季消费趋势营销IP
目标品牌：美妆、食品、家电品牌
输出：先给我15页左右的招商故事线和页序
```

也可以用于文档版方案：

```text
用 $brand-event-pitch，把这个招商PPT扩写成飞书文档形式的招商方案。
要求：保留招商逻辑，补充项目背景、核心亮点、玩法说明、资源权益表、Roadmap和合作流程。
```

如果没有指定文档格式，skill 默认会按招商飞书文档高频结构输出：

```text
高亮块：项目名称、项目亮点、项目介绍、招商信息
一、项目洞察
二、项目介绍
三、核心玩法
四、招商权益概览
五、招商规划
六、下单步骤
七、活动管控规范
```

其中「下单步骤」和「活动管控规范」有固定默认文案，只在用户提供项目名、品牌、价格、档位、收件人、抄送等精确信息时替换占位内容。

也可以用于批量样本学习：

```text
启动 brand-event-pitch 样本学习任务。
入口：<飞书文件夹/知识库/文档/PPT 链接>
范围：只学习招商相关文件
输出：先给学习摘要和可合并结论，不要直接写入 skill
```

### Claude Code 或其他支持 skills 的 agent

如果你的 agent 支持本地 skill 文件夹，把整个 `brand-event-pitch` 文件夹复制到对应的 skills 目录。

Claude Code 用户通常可以尝试：

```bash
mkdir -p ~/.claude/skills
cp -R brand-event-pitch ~/.claude/skills/
```

不同 agent 的触发方式可能不同。如果 `$brand-event-pitch` 不生效，可以直接在对话里说：

```text
请使用 brand-event-pitch 这个 skill，帮我做一个营销活动品牌招商PPT。
```

### 不支持 skills 的 agent

也可以直接把 `brand-event-pitch/SKILL.md` 或 GitHub 链接发给 agent，并要求它按里面的工作流执行：

```text
请阅读这个 SKILL.md，并按照它的流程帮我做品牌招商PPT：
https://github.com/your-org/brand-event-pitch
```

## 更新通知与手动更新

这个 skill 不会主动推送更新到用户电脑。建议使用 GitHub 的通知机制：

1. 打开 GitHub 仓库页面。
2. 点击右上角 **Watch**。
3. 选择 **Custom**。
4. 勾选 **Releases**。

这样每次发布新版 Release 时，安装过的用户都会收到 GitHub 通知，然后手动更新。

当前版本见：

```text
brand-event-pitch/VERSION
```

手动更新方式：

```bash
git pull
rm -rf ~/.codex/skills/brand-event-pitch
cp -R brand-event-pitch ~/.codex/skills/
```

Claude Code 用户可替换为对应目录：

```bash
rm -rf ~/.claude/skills/brand-event-pitch
cp -R brand-event-pitch ~/.claude/skills/
```

维护者发布新版本时，建议同步更新：

- `brand-event-pitch/VERSION`
- `CHANGELOG.md`
- GitHub Release notes

## 推荐输入

最好提供这些信息：

- 活动/节点：比如大促节点、赛事节点、城市活动、暑期消费季、平台 IP。
- 目标品牌：品类或具体品牌。
- 品牌目标：曝光、转化、新品首发、信任背书、内容资产、品类心智。
- 已有资源：话题、H5、搜索、直播间、达人、明星、货架、主会场、PR、线下场。
- 视觉素材：品牌 logo、产品图、活动 KV、参考图片、场地照片、截图；如果没有，请说明是否可以找公开图片或生成主题图。
- 署名/联系人：如果需要展示组织名、负责人、邮箱或电话，请提供准确文字；否则默认不生成。
- 输出形式：故事线、页序、页面文案、HTML slides、招商方案文档、审稿意见。

如果是样本学习任务，推荐提供：

- 入口：飞书/豆包文档、知识库、文件夹、云盘目录、PPT/Slides 链接，或多个入口清单。
- 范围：只学习招商相关文件，还是学习入口内全部文件。
- 输出：只要学习摘要，还是允许把抽象规则写入 skill。
- 权限：确认当前 agent 可访问入口；如果不能访问，请导出 Markdown、DOCX、PPTX、PDF 或页面截图。

## 目录

```text
brand-event-pitch/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
    ├── pitch-method.md
    ├── chrome-rules.md
    ├── image-rules.md
    ├── proposal-doc-method.md
    ├── sample-learning-task.md
    ├── sample-learnings.md
    └── style-presets.md
└── vendor/
    └── frontend-slides/
        ├── LICENSE
        ├── STYLE_PRESETS.md
        ├── animation-patterns.md
        ├── html-template.md
        ├── viewport-base.css
        └── bold-template-pack/
```

## 内置风格

这个 skill 自带两层公开可复用视觉资源：

1. `references/style-presets.md`：专门为招商 PPT 设计的风格方向。
2. `vendor/frontend-slides/`：从 `frontend-slides` 引入的公开模板包和 HTML slides 基础框架。

招商风格方向包括：

- Event Command Center：大事件、增长计划、资源型招商
- Cultural Pop IP：潮流 IP、年轻化活动、社交参与
- Premium Partnership：高预算赞助、战略合作、高端品牌
- Trust Lab：产品证明、溯源、质量背书、科技验证
- Retail Heatwave：销售转化、直播、购物节、优惠资源包
- City Route / Experience Map：城市活动、线下体验、路线打卡

## 图像原则

招商 PPT 默认应该是图像先行：

- 大多数非表格页需要主题相关图片、拼贴、场景图、产品图、地图、UI mockup 或活动视觉。
- 前 3 页不能连续纯文字，至少要有一个强主题视觉。
- 如果没有现成图片，agent 应先理解招商主题，再主动找公开图片 / 生成主题图片 / 使用明确标注的占位图。
- 图片必须和主题相关，例如季节、城市、活动场景、产品品类、人群、文化情绪或品牌参与方式，不能只是通用装饰图。
- 文字应作为判断、标签、数字和注释，不应把整页做成段落报告。

## 飞书招商方案原则

- 默认先用高亮块呈现项目名称、项目亮点、项目介绍、招商信息。
- 用户未指定格式时，严格使用七个大标题：项目洞察、项目介绍、核心玩法、招商权益概览、招商规划、下单步骤、活动管控规范。
- 权益、席位、价格、排期、交付物和限制条件必须表格化或字段化；缺失信息写「待确认」，不编造。
- 招商文档不是 PPT 逐页转写，要改写成销售可转发、品牌可判断、项目组可执行的文档。
- 锁单、下单流程和活动管控规范是执行确定性的一部分，不是可省略附录。

## 样本学习原则

- 如果入口是总文档，先按真实文档 token 去重，再学习。
- 优先学习飞书正文；附件 PDF/PPTX 如果是整页图片，只学习视觉节奏和页型，不臆测正文。
- 学习结果只沉淀抽象方法，不写入私密链接、客户信息、报价明细或不可公开素材。
- 输出应包括覆盖摘要、可合并学习结论、以及建议写入哪些 reference 文件。

## 署名原则

- 默认不在左上角放任何文字。
- 默认不生成页眉、页脚、部门名、平台名、负责人姓名、邮箱、电话或二维码。
- 最后一页默认只保留简洁收尾语和视觉，不放联系人信息。
- 只有当使用者明确提供准确文字并要求展示时，才加入组织名或联系人。

## 注意

发布版只包含从参考方案中抽象出的结构和方法，不包含原始 PDF 样本。

`vendor/frontend-slides/` 来自 `frontend-slides`，遵循 MIT License，版权和许可声明保留在 `vendor/frontend-slides/LICENSE`。
