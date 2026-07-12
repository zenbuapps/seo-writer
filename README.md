# Auto SEO Writer

引導式的 SEO/AEO 文章產生器（Claude Code Skill）。一篇文章＝ **7 個步驟**，每一步都先講清楚「現在要幹嘛」，再給附推薦預設的選項——熟手一路按預設走，速度跟全自動差不多；新手每一步都知道自己在哪、可以介入什麼。

## 七步流程

```
1 定題      問主題／受眾／發佈方式（主題建議來自 AI 對你的既有認識，不預設你有任何內容）
2 研究      宣告後直接進行：掃你的第一手素材＋三路並行研究（SERP 競品／PAA 真實提問／權威數據）
3 大綱確認  ✅ 研究摘要＋大綱＋案例素材狀態（照大綱走／調整／換角度）
4 案例採訪  聊天式問你有沒有真實案例；不想講可讓 AI 編，但編的內容落筆前必逐字給你確認
5 撰文      宣告後直接進行：AEO＋E-E-A-T＋白話引註＋humanize 去 AI 味（humanizer-tw）
6 品檢定稿  ✅ 全文＋18 項品質檢查（<15 分自動修到過）＋歸納寫法逐項給你過目
7 發佈      CMS MCP 草稿或存 .md，回報結果＋下一篇建議
```

**真實案例原則**：第一人稱經驗只能來自你的素材、你親口說的、或你逐字核可過的草稿——AI 不會替你編故事。

也支援**批次模式**：一次丟多個主題，停下來的步驟（3、4、6）整批處理，不會每篇都問一輪。

## 安裝

```bash
git clone https://github.com/zenbuapps/seo-writer.git
cp -r seo-writer/auto-seo-writer ~/.claude/skills/
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
| zenbu MCP | 有連 zenbu 站台 MCP 時，同樣流程對應到 `zenbu_create_article` 等工具，以草稿建立 |
| Markdown 檔 | 存成含 frontmatter（title/slug/keywords/description/Schema）的 `.md`，預設到 `~/Desktop/` |

## 產出規格

- **AEO**：每個 H2/H3 開頭 40–60 字直接回答、問句式標題、段落自包含（AI 可直接引用）
- **E-E-A-T**：第一人稱實測描述、可信來源引用（每 150–200 字一個帶年份的數據點）
- **必備元素**：定義框、FAQ（5 題以上，來自真實 PAA）、JSON-LD Schema（Article + FAQPage + BreadcrumbList）、SEO Meta（Title/Description/Slug）
- **語言**：繁體中文，技術名詞保留英文，數字用阿拉伯數字

## 授權

MIT © Luke Hsu Hao。原始版本收錄於 [lukehsuhao/luke-claude-skills](https://github.com/lukehsuhao/luke-claude-skills)，此 repo 為獨立維護版。
