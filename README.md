# Auto SEO Writer

自動化的 SEO/AEO 文章產生器（Claude Code Skill）。給一個主題，自動完成研究 → 撰文 → humanize（去除 AI 生成痕跡）→ 發佈，全程只有 **2 個確認點**。

適合已經熟悉 SEO 文章產出流程、想要盡量減少互動的情境。想要每一步都參與討論的話，用互動版的 [`seo-aeo-master`](https://github.com/lukehsuhao/luke-claude-skills) 更合適。

## 流程

```
收到主題
  → 快問兩題（受眾＋發佈方式）
  → 三路並行研究（SERP 競品／PAA 真實提問／權威數據）
  → ✅ 確認點 1：研究摘要＋文章大綱
  → 自動撰文（AEO 直答開頭＋E-E-A-T＋Schema＋Meta）
  → humanize 去 AI 味（humanizer-tw）
  → ✅ 確認點 2：全文＋15 項品質檢查（<12 分自動修到過）
  → 發佈（WordPress MCP 或存 .md）
```

也支援**批次模式**：一次丟多個主題，維持總共 2 個確認點（大綱一批確認、成文一批確認），不會每篇都停下來問。

## 安裝

```bash
git clone https://github.com/zenbuapps/claude-skill-auto-seo-writer.git
cp -r claude-skill-auto-seo-writer/auto-seo-writer ~/.claude/skills/
```

裝完後在 Claude Code 說「幫我寫一篇關於 X 的 SEO 文章」就會觸發。

### 建議一起裝：humanizer-tw

流程裡的 humanize 階段會呼叫 [`humanizer-tw`](https://github.com/yelban/humanizer.TW) 這個 skill（原作者 [yelban](https://github.com/yelban/humanizer.TW)），用來去除 AI 寫作痕跡——時代開場白、連接詞濫用、翻譯腔、公式化結構、結尾套話等，讓文字更像台灣人寫的。

```bash
git clone https://github.com/yelban/humanizer.TW.git ~/.claude/skills/humanizer-tw
```

沒裝也能跑：skill 內建了一份濃縮版規則會直接套用，但完整版效果更好。

## 發佈方式

| 方式 | 說明 |
|---|---|
| WordPress MCP | 有連 WordPress MCP server 時，直接建分類/標籤、補站內連結、以草稿發佈（含 Yoast/RankMath SEO meta） |
| Markdown 檔 | 存成含 frontmatter（title/slug/keywords/description/Schema）的 `.md`，預設到 `~/Desktop/` |

## 產出規格

- **AEO**：每個 H2/H3 開頭 40–60 字直接回答、問句式標題、段落自包含（AI 可直接引用）
- **E-E-A-T**：第一人稱實測描述、可信來源引用（每 150–200 字一個帶年份的數據點）
- **必備元素**：定義框、FAQ（5 題以上，來自真實 PAA）、JSON-LD Schema（Article + FAQPage + BreadcrumbList）、SEO Meta（Title/Description/Slug）
- **語言**：繁體中文，技術名詞保留英文，數字用阿拉伯數字

## 授權

MIT © Luke Hsu Hao。原始版本收錄於 [lukehsuhao/luke-claude-skills](https://github.com/lukehsuhao/luke-claude-skills)，此 repo 為獨立維護版。
