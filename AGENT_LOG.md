# AGENT_LOG — 異動紀錄

每次改動這個 repo 的 agent，動工前先讀這裡最上面幾筆、了解目前狀態；完成後在最上面新增一筆，格式如下：

## YYYY-MM-DD — <Claude|Codex> — 一句話標題
- 做了什麼：
- 為什麼：
- 動到的檔案：
- Commit：<commit hash 或連結>

---

## 2026-11-09 — Claude — ch8 範例 8.1 新增均勻分配互動圖表
- 做了什麼：在範例 8.1 之後新增「🎛️ 互動圖表：均勻分配 U(a, b)」：輸入下界 a、上界 b 即時畫出 PDF，輸入 x₁、x₂ 著色 P(x₁ < X < x₂)，附 E(X) 標記與計算過程；含範例 8.1(b)(c) 快捷鍵，以及「區間由 6 拉寬到 24」動畫（示範區間越寬、矩形越矮、總面積恆為 1）。原有靜態圖 8.1 保留。
- 為什麼：Sean 希望範例 8.1 也有類似 Z 轉換動畫的互動圖表。
- 動到的檔案：ch8_continuous_dist.html（新增一個 calc-box 與一段 JS IIFE，未改動既有內容）
- 驗證：</html> 結尾、<script> 4 組、最後 script 通過 node --check；Playwright 實測無 JS 錯誤。
- Commit：2026-11-09 由 My Github Project 部署（見 git log）

## 2026-09-07 — Claude — 建立 Claude/Codex 共用協作機制
- 做了什麼：新增本檔案、AGENTS.md、CLAUDE.md（指向 AGENTS.md）
- 為什麼：Sean 要讓 Codex 加入這個 repo 的開發維護，兩個 agent 需要讀同一份規則、看得到對方的異動紀錄，避免衝突或狀態遺漏
- 動到的檔案：AGENTS.md, CLAUDE.md, AGENT_LOG.md（新增）
- Commit：（見本次 commit）
