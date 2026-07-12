# Changelog

## 1.1.0 — 2026-07-12

第一次實戰跑完整流程（〈使用 AI 的五個層級〉）後的修正。核心教訓：預設寫法太學術、內容只有框架沒有血肉，另補幾個實務洞：

- **引註白話化**（Phase 2 新增 Citation Style）：數據保留來源＋年份，但期刊名、paper 編號、「et al.」不進正文——改用「誰做了什麼研究」的講法。
- **豐富度硬性要求**（Phase 2 新增 Richness Requirements）：每個 H2 至少一個具體物件——可複製的指令、❌/✅ 對照、生活場景清單、或第一人稱故事；純抽象論述過不了確認點 2。
- **第一手素材掃描**（Phase 1 新增 Step 0）：research agent 出發前先找用戶自己的素材（課程字幕、舊文、逐字稿），用戶自己的框架與原話是最強的 E-E-A-T，外部研究是佐證不是主體。
- **Meta Description 中文長度**：150–155 字元是英文規格，中文以 70–80 全形字為準（Google 對 CJK 約 80 字截斷）。
- **品質檢查修正計數並擴充**：原清單實際列了 16 項卻標成 15；補上「每個 H2 有具體物件」與「簡體字／異體字機械掃描」（單一字元如「换」用肉眼會漏，必須跑 regex），現為 18 項、<15 分自動修。
- **.md 發佈的 Schema 網址**（Phase 3 Option B）：存檔時沒有網域，一律用 `https://example.com/[slug]` 佔位＋frontmatter 註記，並在結案報告提醒替換。
- **zenbu MCP 發佈路徑**（Phase 0 / Phase 3 Option A）：明列 zenbu 站台 MCP（`zenbu_create_article` 等）為已知發佈路徑，步驟與 WordPress 一對一對應。

## 1.0.0 — 2026-07-04

從 [lukehsuhao/luke-claude-skills](https://github.com/lukehsuhao/luke-claude-skills) 抽出為獨立 repo，並做以下補強：

- **humanizer-tw 後備方案**：未安裝 `humanizer-tw` 時不再是未定義行為，直接套用 skill 內建的濃縮規則（Phase 2.5）。
- **MCP 工具名彈性**：`mcp__wordpress__*` 明確標註為範例名稱，執行時以 session 實際可用的 WordPress MCP 工具為準；沒接 MCP 就只提供存 .md 選項（Phase 0 / Phase 3）。
- **站內連結**：MCP 發佈流程加一步——先搜站上既有文章，自然置入 2–3 個站內連結再發文（Phase 3 Option A）。
- **批次模式**：新增 Batch Mode 章節。原本 description 就宣稱支援批次，但流程只涵蓋單篇；現在多主題一次跑，維持總共 2 個確認點（大綱一批確認、成文一批確認）。
