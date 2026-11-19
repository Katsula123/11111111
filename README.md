# 先進封裝入門知識 — 個人論文 LLM Wiki 知識庫

本儲存庫結合 **LLM Wiki 知識庫** 與 **極簡風 HTML 簡報（GitHub Pages）**，整理高密度互連（HDI PCB）微盲孔／通孔電鍍填銅與 3D-IC TSV 濺鍍阻隔層之核心論文筆記。

## GitHub Pages 快速發布步驟
1. 將本資料夾內的所有檔案（包含根目錄的 `index.html` 與 `.nojekyll`）上傳至你的 GitHub Repository。
2. 進入 Repository 的 **Settings → Pages**。
3. 在 **Build and deployment** 選擇 **Deploy from a branch**，Branch 選 `main`、資料夾選 `/ (root)` 後按 **Save**。
4. 等待約 1 分鐘，開啟 GitHub Pages 網址即可直接瀏覽《先進封裝入門知識》8 頁極簡風 HTML 簡報。

## 目錄結構
- `index.html` / `slides/先進封裝入門知識.html`：極簡風 HTML 簡報（支援 `←`／`→` 鍵盤切換、目錄跳頁與 KaTeX 公式渲染）
- `.nojekyll`：停用 Jekyll 編譯，確保根目錄 `index.html` 優先呈現
- `AGENTS.md` & `WORKFLOW_SLIDES_GRAPH.md`：知識庫維護與三階段 Graph 簡報生成規範
- `index.md` / `overview.md` / `log.md`：知識庫總目錄、領域總覽與演化日誌
- `paper-*.md` / `concept-*.md` / `compare-*.md`：論文精讀、核心概念與跨論文比較筆記
- `RAW/`：原始論文 PDF 存放區（不可變來源）
