# Changelog — kelly-advisor (skill)

## v0.1.2 — 2026-06-01（對抗式 audit 後優化）

2 個獨立 reviewer audit 後修補：
- kelly-math.md：連續型公式補無風險利率 `(μ−r)/σ²` + 重尾警告；投資型 f>1 說明；2016 實驗加論文出處 + 誠實標註。
- SKILL.md 速查表：連續型公式同步改 `(μ−r)/σ²`。
- 新增英文 README.en.md（全球觸及）+ 包裝（badges / star CTA / trust signal / worked examples）。

## v0.1.1 — 2026-05-31（dogfood hardening）

第一次實測（3 mode）抓到 2 個設計漏洞，照「每個 failure 寫進 skill」原則修補：
- **All-in tie-breaker**：含「all-in / 全押 / 梭哈 / 停掉其他」字眼的決策強制 Mode 3，
  即使表面像 Mode 1/2 配置題。（SKILL.md 路由段 + decision-protocol A 段 + 反例庫）
- **bankroll 定義**：Mode 1 產出格式新增「先定義 bankroll = 該類注的專用資金池」，
  避免把「佔總資產 %」當「佔 bankroll %」算錯基數。
- decision-protocol 新增 G 段 Dogfood 紀錄。

## v0.1 — 2026-05-31（initial）

九位思考者中 7 席圓桌（2026-05-31）的產出。共識：survival-first 下注紀律工具。

- 三模式路由：**Mode 1 Size**（可重複下注 → fractional Kelly）/ **Mode 2 Allocate**（組合配置）/ **Mode 3 Survive**（一次性不可逆 → 拒給數字 + 路由 genius-advisor）。
- Survival-first 七步協定（分類 → 防破產 → 三要素 → full Kelly → 打折 → 壓力測試 → 輸出）。
- 硬規則 R1–R8（先分類 / 下檔優先 / 禁 false precision / 預設分數凱利 / 只賭 surplus / 不適用則路由 / 反割韭菜 / 載入 hao-voice）。
- references：`kelly-math.md` + `decision-protocol.md`。
- 與 genius-advisor 整合：kelly-advisor = 量化前端，genius-advisor = 質化後端。
