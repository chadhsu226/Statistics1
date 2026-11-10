# AGENT_LOG — 異動紀錄

每次改動這個 repo 的 agent，動工前先讀這裡最上面幾筆、了解目前狀態；完成後在最上面新增一筆，格式如下：

## YYYY-MM-DD — <Claude|Codex> — 一句話標題
- 做了什麼：
- 為什麼：
- 動到的檔案：
- Commit：<commit hash 或連結>

---

## 2026-11-10 — Claude — ch8 圖 8.2 改為互動圖＋新增引例
- 做了什麼：在常態分配性質之後新增「📝 引例　三群同學的通勤時間」：A 住附近搭公車 N(35, 6²)、B 外縣市搭客運 N(60, 6²)、C 外縣市騎機車 N(60, 12²)，說明 A vs B 只改 μ（平移）、B vs C 只改 σ（矮胖）。原靜態圖 8.2 改為「🎛️ 互動圖 8.2」：μ（10–90）、σ（3–20）滑桿與數字輸入、A/B/C 快捷鍵、可切換對照曲線、μ±σ 著色、μ 與 σ 標記、橫軸刻度（通勤時間），下方顯示最高點高度與 68%／95% 範圍；縱軸固定，才看得出 σ 改變時的高矮變化。drawFamily() 改寫，沿用原 canvas id 與呼叫點。
- 為什麼：Sean 希望圖 8.2 能自選 μ、σ，並在圖上方有例子對應 35、60、6²、12² 這些數字。
- 動到的檔案：ch8_continuous_dist.html
- 驗證：</html> 結尾、<script> 4 組、最後 script 通過 node --check；Playwright 實測滑桿、輸入框、A/B/C 按鈕皆正常、無 JS 錯誤。
- 已部署：2026-11-10 由 My Github Project 推送

## 2026-11-10 — Claude — ch8 均勻分配改為「PDF → 機率計算 → 平均數與變異數」順序
- 做了什麼：依 Sean 的教學順序調整均勻分配。講義：公式卡拆成 ① PDF ② 機率計算 ③ 平均數與變異數（新增 V(X)=(b−a)²/12、σ=(b−a)/√12）；範例 8.1 的 a 只寫 PDF，平均移到新增的 e（E=6、V=12、σ≈3.46）；習題 8.1 拆出 d（E=7、V=3、σ≈1.73）；Learning Objectives 與 Chapter Summary 同步。筆記：ch8 重點筆記均勻分配區改為三步驟、範例 8.1 加 e、隨堂練習 1 加問變異數、checklist 同步。
- 為什麼：Sean 上課先教 PDF，再教機率計算，最後才講平均數、變異數（標準差）。
- 動到的檔案：ch8_continuous_dist.html、筆記/ch8_重點筆記.html（及 PDF）
- 驗證：講義 </html> 結尾、<script> 4 組、最後 script 通過 node --check，Playwright 實測無 JS 錯誤；筆記仍為 4 頁 A4、無溢頁。
- 已部署：2026-11-10 由 My Github Project 推送（講義 + notes/ch8_notes.html）

## 2026-11-10 — Claude — 目錄頁 ch8~10 新增「隨堂筆記」按鈕
- 做了什麼：上傳 Sean 製作的 ch8、ch9、ch10 重點筆記為 notes/ch8_notes.html、notes/ch9_notes.html、notes/ch10_notes.html；index.html 中 ch8~10 卡片改為 div（整張卡片仍連到講義），在「📖 講義」右側新增「📝 隨堂筆記」按鈕；手機版只顯示筆記按鈕。
- 為什麼：Sean 希望學生能從目錄頁直接開啟隨堂筆記。
- 動到的檔案：index.html、notes/（新增）
- 來源：teaching 115_1\Statistics1\筆記\chN_重點筆記.html（PDF 未上傳）
- Commit：見本次 commit

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
