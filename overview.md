# 領域全景總覽 (Overview)

> 本頁面為剛踏入「先進封裝與高密度互連金屬化」領域的研究生設計，串連目前知識庫已讀的三篇核心碩博士論文，建立從乾製程成膜到濕製程電鍍填孔的整體地圖。

## 1. 研究領域核心問題
在電子產品輕薄短小與 3D-IC 異質整合趨勢下，無論是印刷電路板 (HDI PCB) 的微盲孔／通孔，還是矽晶片上的直通矽晶穿孔 (TSV)，都面臨同一個物理難題：**「當孔洞越來越窄且越來越深（高深寬比 High Aspect Ratio）時，如何把金屬材料均勻且無空洞地送進孔底？」**

## 2. 關鍵技術與概念脈絡
- **乾製程前置成膜（PVD 濺鍍）**：在 3D-IC TSV 電鍍前，需先濺鍍 Ti 阻隔層與 Cu 種子層，克服 Bosch 蝕刻產生的扇貝 (Scallop) 側壁陰影。詳見 [[concept-step-coverage-tsv]]。
- **濕製程電鍍填孔（Superfilling & CDA）**：透過強制對流調節陰極表面的氯離子覆蓋率，搭配抑制劑 (PEG)、加速劑 (SPS) 與雙平整劑 (NTBC + ABPV)，讓孔底沉積快於孔口，避免空洞 (Void) 與細縫 (Seam)。詳見 [[concept-convection-dependent-adsorption]] 與 [[concept-bottom-up-superfilling]]。
- **跨製程對照**：[[compare-microvia-vs-pth-plating]] 解析盲孔與通孔同鍍槽的酸銅比衝突；[[compare-pcb-microvia-vs-3dic-tsv]] 對比 PCB 濕製程與 TSV 乾製程的輸送瓶頸。

## 3. 新手建議閱讀順序
1. 先讀 [[paper-2011-forced-convection-microvia-cu]]，建立「流場、擴散、電遷移」的基本直覺與縱橫比 1.2 的物理極限觀念。
2. 接著讀 [[paper-2017-one-bath-microvia-pth-cu]]，理解電化學分析（CP/CV）、雙平整劑協同機制與田口實驗設計如何解決工程配方衝突。
3. 再讀 [[paper-2012-tsv-ti-sputtering-coverage]]，把視野從 PCB 濕製程延伸至 3D-IC TSV 電鍍前的 PVD 濺鍍阻隔層製程。
