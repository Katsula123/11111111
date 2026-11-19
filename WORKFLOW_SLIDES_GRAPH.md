# WORKFLOW_SLIDES_GRAPH.md — Graph 簡報生成規範（定案版）

本規範定義從 LLM Wiki 產出**極簡風 HTML 專題簡報**的三階段 Graph 狀態機流程，確保每頁簡報嚴格植基於已讀論文，並在關鍵節點保留人工確認（HITL）。

## 1. 共用狀態（Graph State）
- `topic` / `target_audience`：簡報主題與對象（預設為剛入門的研究生／專題報告）。
- `wiki_sources[]`：本次引用的 `paper-*.md`、`concept-*.md`、`compare-*.md`。
- `missing_gaps[]`：偵測到缺乏 Wiki 支撐的論點清單。
- `outline_md` / `outline_approved`（HITL 1）。
- `slide_content_md` / `content_approved`（HITL 2）。
- `retry_count_content`（上限 2）/ `retry_count_html`（上限 2）。

## 2. 三階段節點與檢查閘門

### Stage 1：Wiki 檢索與大綱（Outline）
- **Node 1（檢索與大綱）**：讀取 `index.md` 鎖定相關頁面，規劃頁數、每頁核心主張與對應來源。
- **Node 2（缺口檢查 + HITL 1）**：
  - **缺口處理（直接暫停）**：若發現關鍵論點標記為 `[Wiki 尚無此資料]`，立即暫停 Graph，列出缺口與建議先讀／攝取的論文清單，待補齊後再恢復。
  - **HITL 1**：無缺口時，暫停並請使用者核准大綱（或退回 Node 1 修改）。

### Stage 2：逐頁簡報內容（Slide Content）
- **Node 3（內容撰寫）**：依核准大綱精讀各 Wiki 頁，產出每頁標題結論、Markdown 比較表、LaTeX 公式與講稿要點。
- **Node 4（Wiki-Only 檢查 + HITL 2）**：
  - **自動檢查**：稽核是否嚴格僅用 Wiki 內容、量化數據是否附帶製程條件、矛盾處是否並列條件差異、單頁密度是否過載。
  - **退回上限**：未通過時局部退回 Node 3 重寫，**最多自動重試 2 次**；超過 2 次轉交人工決定。
  - **HITL 2**：自動檢查通過後，暫停並請使用者審閱定稿內容。

### Stage 3：極簡風 HTML 生成與驗收（HTML Build & QA）
- **Node 5（極簡風 HTML 生成）**：產出純白底（`#FFFFFF`）、淺灰卡片（`#F9FAFB`）、牛津藍點綴（`#1E3A8A`）、支援 KaTeX 公式、16:9 鍵盤導航（`←`/`→`）與列印的單檔 HTML 簡報。
- **Node 6（排版 QA 驗收）**：檢查 KaTeX 語法閉合、表格溢出與層級對比；未通過退回 Node 5 微調（**最多自動重試 2 次**）。
