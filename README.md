# Brand Event Pitch Skill

用于创建和打磨「品牌招商 / 赞助合作 / 联合营销活动」相关方案的 agent skill。

它适合这些任务：

- 生成品牌招商 PPT 的故事线和页序
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

## 推荐输入

最好提供这些信息：

- 活动/节点：比如大促节点、赛事节点、城市活动、暑期消费季、平台 IP。
- 目标品牌：品类或具体品牌。
- 品牌目标：曝光、转化、新品首发、信任背书、内容资产、品类心智。
- 已有资源：话题、H5、搜索、直播间、达人、明星、货架、主会场、PR、线下场。
- 视觉素材：品牌 logo、产品图、活动 KV、参考图片、场地照片、截图；如果没有，请说明是否可以找公开图片或生成主题图。
- 署名/联系人：如果需要展示组织名、负责人、邮箱或电话，请提供准确文字；否则默认不生成。
- 输出形式：故事线、页序、页面文案、HTML slides、审稿意见。

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

## 署名原则

- 默认不在左上角放任何文字。
- 默认不生成页眉、页脚、部门名、平台名、负责人姓名、邮箱、电话或二维码。
- 最后一页默认只保留简洁收尾语和视觉，不放联系人信息。
- 只有当使用者明确提供准确文字并要求展示时，才加入组织名或联系人。

## 注意

发布版只包含从参考方案中抽象出的结构和方法，不包含原始 PDF 样本。

`vendor/frontend-slides/` 来自 `frontend-slides`，遵循 MIT License，版权和许可声明保留在 `vendor/frontend-slides/LICENSE`。
