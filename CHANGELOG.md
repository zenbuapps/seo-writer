# Changelog

## 1.0.0 — 2026-07-04

從 [lukehsuhao/luke-claude-skills](https://github.com/lukehsuhao/luke-claude-skills) 抽出為獨立 repo，並做以下補強：

- **humanizer-tw 後備方案**：未安裝 `humanizer-tw` 時不再是未定義行為，直接套用 skill 內建的濃縮規則（Phase 2.5）。
- **MCP 工具名彈性**：`mcp__wordpress__*` 明確標註為範例名稱，執行時以 session 實際可用的 WordPress MCP 工具為準；沒接 MCP 就只提供存 .md 選項（Phase 0 / Phase 3）。
- **站內連結**：MCP 發佈流程加一步——先搜站上既有文章，自然置入 2–3 個站內連結再發文（Phase 3 Option A）。
- **批次模式**：新增 Batch Mode 章節。原本 description 就宣稱支援批次，但流程只涵蓋單篇；現在多主題一次跑，維持總共 2 個確認點（大綱一批確認、成文一批確認）。
