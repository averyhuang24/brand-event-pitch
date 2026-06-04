# Brand Event Pitch Skill

用于创建和打磨「品牌招商 / 赞助合作 / 联合营销活动」相关方案的 Codex skill。

它适合这些任务：

- 生成品牌招商 PPT 的故事线和页序
- 改写营销活动招商方案
- 审查招商 PPT 的商业逻辑、资源表达和页面顺序
- 将成熟故事线继续扩展成 HTML slides

## 安装

把 `brand-event-pitch` 文件夹复制到本地 Codex skills 目录：

```bash
mkdir -p ~/.codex/skills
cp -R brand-event-pitch ~/.codex/skills/
```

然后在对话里这样使用：

```text
用 $brand-event-pitch，帮我做一个营销活动品牌招商PPT。
活动是：夏季消费趋势营销IP
目标品牌：美妆、食品、家电品牌
输出：先给我15页左右的招商故事线和页序
```

## 推荐输入

最好提供这些信息：

- 活动/节点：比如大促节点、赛事节点、城市活动、暑期消费季、平台 IP。
- 目标品牌：品类或具体品牌。
- 品牌目标：曝光、转化、新品首发、信任背书、内容资产、品类心智。
- 已有资源：话题、H5、搜索、直播间、达人、明星、货架、主会场、PR、线下场。
- 输出形式：故事线、页序、页面文案、HTML slides、审稿意见。

## 目录

```text
brand-event-pitch/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── pitch-method.md
    └── sample-learnings.md
```

## 注意

发布版只包含从参考方案中抽象出的结构和方法，不包含原始 PDF 样本。
