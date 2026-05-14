# Upstream Merge Log

Track merges from upstream repository `ZhuLinsen/daily_stock_analysis`.

## [2026-04-03] Initial Setup

- Created evening shift workflow: `.github/workflows/daily_analysis_evening.yml`
- Configured dual-schedule architecture:
  - **Main Task**: UTC 10:00 (Beijing 18:00), uses `STOCK_LIST` secret, full notification channels
  - **Evening Task**: UTC 11:00 (Beijing 19:00), uses `EVENING_STOCK_LIST` secret, PushPlus only
- Secrets configured:
  - `STOCK_LIST` - Main task stock list
  - `EVENING_STOCK_LIST` - Evening task stock list
  - `PUSHPLUS_TOKEN` - PushPlus notification token (evening only)

---

## [2026-04-07] PushPlus Configuration Update

- **Removed** `PUSHPLUS_TOKEN` from main workflow (`daily_analysis.yml`)
- **Purpose**: Isolate PushPlus notifications for evening task only
- **Note**: After upstream sync, verify main workflow does not re-add PushPlus config

---

## [2026-05-14] Upstream Sync

- Merged from: `ZhuLinsen/daily_stock_analysis@main`
- Upstream commit: `60d8211` (docs: close notification issue 1200)
- Our HEAD before merge: `0b3b2e1` (Update daily_analysis_evening.yml)
- 114 commits behind, merged cleanly with 1 conflict in `daily_analysis.yml`
- Conflict resolution:
  - Accepted upstream: ntfy, Gotify notification channels (new features)
  - Re-removed: `PUSHPLUS_TOKEN` from main workflow (per config protection policy — evening task only)
  - Preserved: `daily_analysis_evening.yml`, `MERGE_LOG.md` (upstream deleted, ours kept)
- Sync branch: none (direct merge to main)
- Verified: evening workflow intact, SKILL.md auto-merged with updated import paths

## [2026-04-07] PushPlus Configuration Update
