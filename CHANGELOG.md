# Changelog — kelly-advisor (repo)

## v0.1.2 — 2026-06-01（開源後優化 — 對抗式 audit + 全球觸及）

**對你的意義（白話）**：這版讓工具的數學更精確、英文使用者也讀得懂、可信度信號更完整。
**Origin**：開源上 GitHub 後，跑 2 個獨立 reviewer 做對抗式 audit（數學正確性 8/10 + 開源質量 7.5/10）。

### 新增 / 改進
- **英文版 `README.en.md`**（完整翻譯）+ 中文 README 頂部加英文 TL;DR + 雙向語言切換連結（解鎖全球觸及）。
- **數學精確化**（audit 抓到，已修）：
  - 連續型公式 `f*≈μ/σ²` → 標明 `(μ−r)/σ²`（超額報酬須先扣無風險利率）+ 重尾資產警告。
  - 投資型 f 可 >1 的說明（單筆非全損 → 可槓桿；賭注型全損 → f≤1）。
  - 2016 硬幣實驗加完整論文出處（Haghani & Dewey）+ 誠實標註「數字未逐一核對原文，引用以原論文為準」。
- **包裝**：README 加 badges（MIT / Claude Skill / version / PRs）、star CTA、作者 trust signal、姊妹 skill genius-advisor 連結 + worked examples（Mode 1 給數字 vs Mode 3 拒答對比）。
- **整合**：genius-advisor `_index.md` 加 kelly-advisor 雙向 pointer（v0.7.6）。

### 仍待辦
- README 對話截圖（視覺 demo，需 Hao 跑一次截圖）。
- 2016 數字對原論文逐字核對。

## v0.1.1 — 2026-05-31（dogfood hardening）
首次實測（3 mode）抓到 2 漏洞並修補：① All-in tie-breaker（含「all-in/全押/停掉其他」→ 強制 Mode 3）② Mode 1 先定義 bankroll（避免把「佔總資產%」當「佔 bankroll%」）。詳見 `kelly-advisor/CHANGELOG.md` + decision-protocol G 段。

## v0.1 — 2026-05-31（initial）

第一版。設計來源：2026-05-31 genius-advisor 7 席圓桌
（Naval / Munger / Buffett / Jobs / Kiyosaki / MrBeast / Belfort）。
圓桌共識：做成 **survival-first 下注紀律工具**，不是萬用神諭計算機。

### 新增
- `kelly-advisor/SKILL.md` — 主 skill：三模式路由（Size / Allocate / Survive）+ survival-first 七步協定 + 硬規則 R1–R8 + genius-advisor 整合 + 反割韭菜立場。
- `kelly-advisor/references/kelly-math.md` — 凱利公式三型、f*≤0 判讀、分數凱利對照表、破產/遍歷性數學、2016 偏誤硬幣實驗、計算誠實檢查清單。
- `kelly-advisor/references/decision-protocol.md` — 分類決策樹、Mode 1/2/3 操作格式、5 個實戰範例（投資部位 / 7 產品時間配置 / 換工作拒答 / all-in 創業 / SKU 廣告加碼）、反例庫。
- `README.md` / `LICENSE`（MIT）/ `.gitignore`（排除 for-me/）。
- `references/for-me/strategy-and-monetization.md` — 私有：圓桌全紀錄 + 變現策略 + R18 治理（不進公開 repo）。

### 設計決策
- **核心 = Mode 3 的「拒絕回答」**：對不可重複/不可逆/機率不可知的決策不給數字，改防破產清單 + 路由 genius-advisor。這是與一般凱利計算機最大的差異（Jobs 席：砍掉「萬用」框架）。
- **預設 fractional Kelly**（R4）、**下檔優先**（R2）、**禁 false precision**（R3）、**只賭 surplus**（R5）。
- **反割韭菜**（R7）：不報明牌、不保證報酬，與作者既有使命一致。

### 待辦（v0.2+ 候選）
- genius-advisor `_index.md` 加反向 pointer（投資/資產領域 → 呼叫 kelly-advisor 做 sizing）。
- 實戰跑 3–5 次後補反例庫。
- （gated）變現層：Pro 模板包 / 書章節 / 錄製課，見 for-me 策略檔。
