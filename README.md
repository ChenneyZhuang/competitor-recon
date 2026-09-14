# competitor-recon 竞品调研

Run competitor reconnaissance before building any feature: the review sections of existing products are the cheapest requirements research that exists.

动手做功能之前先跑竞品侦察：现有产品的用户评论区，是世界上最便宜的需求调研。

## Why / 为什么

Marketing pages state intentions; user reviews state outcomes. One grounded complaint is worth more than any amount of feature-page copy — and a complaint repeated by three independent users is an unmet need you can build against.

营销页写的是意图，用户评论写的是结果。一条有出处的真实抱怨，胜过整页功能文案；三个互不相识的用户抱怨同一件事，就是一个可以动手满足的未满足需求。

## The method / 方法（4 步）

1. **Enumerate** 3–6 competitors — search English *and* Chinese sources; one language samples half the market.
2. **Extract** per competitor: features, pricing (numbers, not "contact us"), positioning, and user complaints **with source links**.
3. **Cluster** complaints by the underlying need, ranked by frequency.
4. **Deliver**: comparison table + copy-worthy list + skip list. A feature idea enters the build list only with a cited user complaint behind it.

## Worked example — recon on an open-source ledger app (2026-09, real run)

Sources actually fetched during the run: V2EX threads (via curl), the target's GitHub issue tracker (via API — reaction counts double as frequency statistics), community forums.

| Complaint cluster | Evidence | Verdict |
|---|---|---|
| Ads / subscription inflation driving users out | multiple independent forum posts naming the incumbents | differentiate: stay clean, price predictably |
| "AI auto-capture might be wrong, I re-check manually" | feature request with 👍×3 in the target's own tracker | build: recognition → confirmation loop |
| Reimbursement / refund flows too complex | complaints across two products, praise for a third's | build: expense-return workflow done simply |
| Multi-currency locked behind a paywall | a long-time user defected over exactly this | skip: no demand evidence beyond the wall itself |

The run produced the full comparison table plus a skip list with reasons — 3 build ideas, each cited; 3 skips, each justified.

## Rules that make it work / 让它生效的规则

- Reviews outrank marketing pages; conflicts are recorded as claims.
- Complaint clusters are the finding — one is anecdote, three is a need.
- Issue trackers are goldmines: a 👍 count is a frequency statistic for free.
- Tool blocked? Switch clients, not sources (curl, public APIs). The evidence bar never drops.

## Honest limitations / 如实说明局限

- Review sites and forums rate-limit bots; some evidence may come from search snippets instead of full threads — those citations are marked as such.
- Reaction counts measure engagement, not market size; a quiet competitor may simply have no community.
- English+Chinese covers our ecosystems; other markets (JP/KR/EU) are not sampled.

评论站对爬虫限流；部分证据可能来自搜索摘要而非完整帖子——这类引用会明确标注。反应数衡量参与度而非市场规模。我们只覆盖中英两个生态。

## Install / 安装

```bash
git clone https://github.com/ChenneyZhuang/competitor-recon ~/.claude/skills/competitor-recon
```

One SKILL.md. Needs only web search and any fetch client. MIT. v0.2.0 — live-tested end-to-end.

单个 SKILL.md，只需搜索与抓取能力。MIT 许可，v0.2.0，完整实测通过。
