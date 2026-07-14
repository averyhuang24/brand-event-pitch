# Trend MCP Pack

Use this integration note when the user wants the skill to search Xiaohongshu/RedNote or Douyin before招商 ideation, especially when the end users are non-technical.

This pack is an **optional read-only trend research layer**. It should not turn the招商 skill into a social-media publishing or account-operations agent.

## First Principle

The user should only need to say:

```text
Install brand-event-pitch and enable trend research.
```

The installing agent/maintainer should handle MCP setup, login, and capability checks. If the environment cannot support MCP, the skill should fall back to web-indexed research or user-provided links/screenshots.

## Recommended Sources

### Xiaohongshu / RedNote

Prefer `xpzouying/xiaohongshu-mcp` when platform-native Xiaohongshu research is needed.

Why it is currently the best default:

- It is purpose-built for xiaohongshu.com.
- It supports keyword search, recommendation list, post detail, interaction data, comments, and user profile.
- Its README recommends an `x-mcp` browser plugin route for non-technical users.
- It can expose a local HTTP MCP endpoint such as `http://localhost:18060/mcp`.

Safe read-only allowlist for this skill:

- `check_login_status`
- `get_login_qrcode`
- `list_feeds`
- `search_feeds`
- `get_feed_detail`
- `user_profile`

Do not use by default:

- `publish_content`
- `publish_with_video`
- `post_comment_to_feed`
- `reply_comment_in_feed`
- `like_feed`
- `favorite_feed`
- cookie deletion or account-changing actions unless needed for setup and approved by the user

### Douyin

Use a Douyin MCP only for read/search/analysis. Candidate projects should be evaluated in this order:

1. A tool that supports searching Douyin videos, video details, comments, creator analysis, and transcript/metadata extraction.
2. If search is unreliable, use a link-based extractor for user-provided Douyin links.

Known candidate types:

- Search/detail/comment oriented: `pazwusimple-netizen/douyin-mcp` style projects.
- Link parsing/transcript oriented: `yzfly/douyin-mcp-server` style projects.

Safe read-only allowlist:

- search videos
- get video detail
- get comments
- get creator/profile summary
- extract title/caption/transcript/metadata from a user-provided link

Do not use by default:

- upload/publish video
- comment
- like/favorite/follow
- private messaging
- account growth/automation
- bulk scraping beyond the minimum needed for trend ideation

## Installation Strategy For Non-Technical Users

Do not ask users to understand MCP. Ask the installing agent to do these steps:

1. Detect the user's AI client: Codex, Claude Code, Cursor, Cline, Gemini CLI, OpenClaw, or other.
2. Install the `brand-event-pitch` skill.
3. Install the Xiaohongshu MCP using the lowest-friction route available:
   - browser plugin route for non-technical users if supported by the chosen project
   - prebuilt binary or Docker route for technical users
   - source build only when the previous routes are unavailable
4. Login to Xiaohongshu through the MCP's official login flow. Do not ask the user for cookies or passwords in chat.
5. Install a read-only Douyin MCP. Prefer search/detail/comment capability; otherwise install a link parser and require user-provided Douyin links.
6. Configure the AI client to connect to the MCP server endpoints or stdio commands according to that client's MCP format.
7. Verify by running:
   - Xiaohongshu: login status, one keyword search, one post detail.
   - Douyin: one keyword search or one user-provided link parse.
8. Report enabled capability as:
   - `xiaohongshu: platform-native`
   - `douyin: platform-native`
   - `douyin: link-only`
   - or `web-indexed fallback only`

## Codex Notes

Codex MCP configuration may vary by version and workspace policy. Installing agents should inspect the local Codex MCP configuration style before editing it.

If Codex supports HTTP MCP endpoints in the current environment, connect the Xiaohongshu server URL directly, for example the endpoint exposed by the upstream MCP.

If Codex only supports command/args stdio MCP entries in the current environment, prefer a stdio-compatible MCP server or a small local bridge only after reviewing the bridge code. Do not silently add arbitrary third-party scripts.

After modifying Codex MCP config, restart Codex so new MCP tools appear.

## Runtime Behavior

When the trend layer is available, the skill should run this sequence before ideation:

1. Search 3-5 theme keywords on Xiaohongshu.
2. Search 3-5 theme keywords on Douyin.
3. Pull details/comments/transcripts for the strongest 5-10 signals.
4. Cluster by content mechanism, not by title.
5. Generate招商 ideas with source confidence and trend evidence.

When the trend layer is not available:

1. Say which platform-native capability is missing.
2. Use web-indexed research if available.
3. Ask for 5-20 links/screenshots/topic notes if web-indexed research is too weak.

## Security And Compliance Gate

Before enabling any third-party MCP, the installing agent should check:

- repository activity and maintainer signals
- license
- install method
- whether it requests cookies, tokens, browser sessions, or account credentials
- whether it exposes write actions
- whether it stores data locally or remotely
- whether the user is comfortable logging in through the tool

For this skill's default trend research mode, only read actions are necessary. Refuse or ask for separate confirmation if a tool tries to perform write actions.
