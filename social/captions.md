# Captions — copy, paste, post

Links: product repo first (people want to inspect code), the site page second.
Media: `../assets/fleetmux-demo.gif` (16:9, README/X/Reddit), `../assets/social/fleetmux-demo-vertical.mp4` (9:16, 抖音/小红书 video), `cards/card-*.png` (小红书 图文).

---

## Show HN (fleetmux)

**Title** (≤80 chars):
`Show HN: FleetMux – tmux status bar that shows which of your AI agents are waiting on you`

**URL:** https://github.com/xiaolongnk/fleetmux

**First comment (post it yourself right after submitting):**

> I run 6–8 Claude Code / Codex panes at once across ~40 projects. The thing that actually cost me time wasn't the agents — it was not knowing which pane was waiting for me. I'd click through them one by one.
>
> FleetMux is a tmux setup (one command, idempotent, CI installs it twice and diffs) whose status bar counts agent panes and marks the ones that need you: `⬡ Claude 2 ●1  ◆ Codex 2 ●1`. `prefix+Enter` jumps to the next one.
>
> Two things I got wrong first that might be useful to others:
> - Don't detect agents by pane *title*. Claude Code sets the title to the conversation topic, Codex to the task. On my server, 1 of 28 agent panes had the agent's name in the title. `#{pane_current_command}` is unambiguous.
> - tmux has no per-pane activity clock, but every agent prints the same tells on screen — "esc to interrupt" means busy, "Do you want to proceed?" means it's asking you. `capture-pane` on the last 8 lines is enough, and 29 panes probe in 0.4 s.
>
> If you already have a tmux config you like, the status bar alone is a TPM plugin: https://github.com/xiaolongnk/tmux-agent-status
>
> Longer write-up with the numbers: https://xiaolongnk.github.io/agent-fleet/

## Show HN (SuperHarness) — post on a different day

**Title:** `Show HN: SuperHarness – keep an AI agent's always-loaded context flat while it manages 40 projects`

**URL:** https://github.com/xiaolongnk/SuperHarness

**First comment:**

> Every line in CLAUDE.md is a tax paid on every session. Past the fourth project, the reflex fix — paste one more paragraph in — makes the prompt longer until nothing in it fires reliably.
>
> SuperHarness splits every layer (rules, skills, memory, knowledge, task boards) into a small always-loaded index and a library that loads only on match, and ships a CLI that measures it: `superharness check` exits 1 when the always-loaded bytes grow past baseline. Measured: 12.6 KB to start, +94 bytes per added project.
>
> `npm create superharness my-hub` scaffolds the repo, including a SessionStart hook so the core actually loads. There's a behavioral test that runs a real `claude -p` inside a scaffold and checks the claims — a fresh session recovering a parked item down to `file:line` and commit from the task board is the one that convinced me.
>
> Write-up: https://xiaolongnk.github.io/agent-fleet/

## Reddit r/ClaudeAI (upload the GIF natively, don't just link)

**Title:** `I run 8 Claude Code + Codex panes at once. Made tmux tell me which one is waiting for me.`

**Body:**

> Status bar counts the agent panes and marks the ones that need me (idle or asking for approval) — `⬡ Claude 2 ●1  ◆ Codex 2 ●1` — and `prefix+Enter` jumps to the next one.
>
> Detection is by the pane's running command, not its title (Claude Code titles panes with the conversation topic, so titles are useless), and state is read from the last lines of the screen ("esc to interrupt" = busy, "Do you want to proceed?" = needs you).
>
> One-command install: https://github.com/xiaolongnk/fleetmux
> Just the status bar as a TPM plugin: https://github.com/xiaolongnk/tmux-agent-status
>
> Happy to answer questions about the detection — it took a couple of wrong turns.

## X / Twitter (one post, GIF attached)

> Running 8 AI coding agents in tmux and not knowing which one is waiting for you is the whole problem.
>
> FleetMux: status bar counts agent panes, marks the ones that need you, prefix+Enter jumps there. Claude Code · Codex · Cursor · Gemini.
>
> One command: github.com/xiaolongnk/fleetmux

Follow-up reply (thread):
> Just the status bar for your own tmux config: `set -g @plugin 'xiaolongnk/tmux-agent-status'`
> How it decides busy / needs-you / idle: xiaolongnk.github.io/agent-fleet/

---

## 小红书（图文：cards/card-1…6.png，封面用 card-1）

**标题（≤20 字）：** `一个人同时跑 8 个 AI agent 是什么体验`

**正文：**

> 我每天同时开着七八个 Claude Code / Codex 的窗口，四十个项目轮着来。真正费时间的不是 agent 本身，是我不知道哪个窗口在等我——只能一个个点过去看。
>
> 所以做了三个开源工具（都是 MIT）：
>
> 🟦 FleetMux —— 一条命令装好的 tmux 配置，状态栏直接显示「⬡ Claude 2 ●1」：两个 Claude 窗口，一个在等我审批。按一下跳过去。
> 🟩 tmux-agent-status —— 只要这个状态栏？一行插件加进你自己的 tmux。
> 🟧 SuperHarness —— 管 40 个项目的"总控"：需求自动路由到项目，新会话能接着上次的活干，而且 CLAUDE.md 不会越来越长（实测每加一个项目只多 94 字节）。
>
> 里面有两个踩过的坑，图 3 和图 4 讲了。
> 全部代码和完整介绍：xiaolongnk.github.io（主页上有中文版）
>
> #AI编程 #ClaudeCode #Codex #tmux #开源 #AIAgent #开发者工具 #效率工具

## 抖音 / 视频号（竖版视频 fleetmux-demo-vertical.mp4，13 秒）

**口播/字幕（三句）：**
1. 同时跑八个 AI agent，最烦的是不知道哪个在等你。
2. 这个 tmux 状态栏直接告诉你：两个 Claude，一个在等审批；一个 Codex 已经干完了。
3. 按一下，跳过去。开源，一条命令装好，主页在评论区。

**评论区置顶：** `github.com/xiaolongnk/fleetmux ｜ 完整介绍 xiaolongnk.github.io`

## 即刻 / V2EX（链接 + 短文）

**V2EX 标题（分享创造节点）：** `FleetMux：让 tmux 状态栏告诉你哪个 AI agent 在等你（Claude Code / Codex / Cursor / Gemini）`

> 同时跑多个 agent 窗口的人应该都有这个痛点：不知道哪个在等你审批、哪个已经干完了。
> 做了个 tmux 配置，状态栏按窗口里跑的命令识别 agent（不靠标题——Claude Code 的标题是对话主题，没法用），从屏幕最后几行判断它是忙、在问你、还是空闲，然后 prefix+Enter 跳到下一个需要你的。
> 一条命令装，跑两遍也不会重复改配置（CI 里真装两遍做 diff）。只要状态栏的话有 TPM 插件版。
> github.com/xiaolongnk/fleetmux ｜ 介绍：xiaolongnk.github.io/zh/agent-fleet/

---

## Timing

- HN: Tue–Thu, 8–10am US Eastern. FleetMux first (visual, simple); SuperHarness a week later.
- Reddit + X the same day as HN, within the hour.
- 小红书/抖音/即刻: the next day, mention the HN thread if it did well.
- Reply to every comment for the first 48 h. Issues opened in the first two weeks get same-day answers.
