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
  - `PUSHPLUS_TOKEN` - PushPlus notification token

---

## [Pending] Upstream Sync

- Merged from: `ZhuLinsen/daily_stock_analysis@main`
- Upstream commit: [待填写]
- Changes: [待填写]
- Sync branch: [待填写]
