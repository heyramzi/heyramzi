Read `/Users/ramzi/.claude/stats-cache.json` and present a clean usage dashboard. Follow this exact format — no extra commentary before or after:

---

```
╔══════════════════════════════════════════════════╗
║  UPSYS / STUDIO  ·  Claude Code Usage            ║
╚══════════════════════════════════════════════════╝
```

## Overview

| Metric | Value |
|--------|-------|
| Total sessions | {totalSessions} |
| Total messages | {totalMessages formatted with commas} |
| Active since | {firstSessionDate formatted as "MMM D, YYYY"} |
| Peak session | {longestSession.messageCount} msgs · {longestSession.duration converted to hours/mins} |

---

## Last 7 Days

Show a compact table with only the last 7 days of `dailyActivity`, most recent first.

| Date | Sessions | Messages | Tool Calls |
|------|----------|----------|------------|
| ... | ... | ... | ... |

Include a sparkline-style ASCII bar chart for messages (scale bars to the max value in range, use `█` chars, max 20 wide).

---

## Models

Show aggregate stats from `modelUsage`. For each model, display:
- Short model name (e.g. "Opus 4.6", "Sonnet 4.6")
- Input tokens (formatted, e.g. "1.5M")
- Output tokens (formatted)
- Cache reads (formatted)

| Model | Input | Output | Cache Reads |
|-------|-------|--------|-------------|

---

## Peak Hours

From `hourCounts`, show the top 5 most active hours in this format:
`HH:00  ████████████  N sessions`

Scale bars to the max count. Label times in 12h format.

---

Rules:
- Format all large numbers with K/M suffixes (e.g. 278K, 1.5M)
- Convert duration ms to "Xh Ym" format
- Use only standard markdown (tables, code blocks, headers)
- Keep it tight — no fluff, no explanations of what the data means
- Today's date is $CURRENT_DATE
