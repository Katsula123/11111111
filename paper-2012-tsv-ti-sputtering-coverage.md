---
title: "How process parameters influenced step coverage performance of sputtered Titanic thin-film in TSV of 3D-IC"
authors: ["Chung-Shien Chiang (江宗憲)", "Chih Chen (陳智)"]
year: 2012
venue: "國立交通大學工學院半導體材料與製程設備學程碩士論文"
tags: [tsv, 3d-ic, pvd, sputtering, titanium, step-coverage, bosch-scallop]
status: read
raw_source: "RAW/鈦金屬在TSV直通矽晶穿孔中的金屬薄膜覆蓋率研究.pdf"
---

# 鈦金屬在 TSV 直通矽晶穿孔中的 PVD 覆蓋率研究 (2012)

## 給新手的背景脈絡（為什麼這篇重要？）
在 3D-IC 封裝中，直通矽晶穿孔 (Through-Silicon Via, TSV) 在電鍍填銅之前，必須先用物理氣相沉積 (PVD) 在孔內濺鍍一層**鈦 (Ti) 阻隔層**與**銅種子層**。但傳統 PVD 濺鍍粒子是「直線飛行 (Line of Sight)」，遇到 Bosch 深蝕刻產生的扇貝狀 (Scallop) 側壁與高深寬比通孔時，粒子極難到達孔底與側壁。業界通常得加裝昂貴硬體（如準直管、長投法、IMP 線圈）；本論文則驗證：**在不增加任何硬體設備的標準 300mm 磁控濺鍍機台下，調變製程參數能把 TSV 底部覆蓋率拉到多高？**

## 核心方法與物理機制
- **設備與觀測指標**：使用力鼎精密 Robusta 300 標準 300mm 磁控濺鍍腔體，以掃描式電子顯微鏡 (SEM) 量測平面膜厚 $t$ 與通孔底部膜厚 $b$，計算**底部階梯覆蓋率 (Bottom Step Coverage, B.S.C.)**：
  $$\text{B.S.C.} = \frac{b}{t} \times 100\%$$
- **為何重視孔底厚度？**：實務上會用第二階段「反濺鍍 (Re-sputtering / Sputter Etch)」把孔底的 Ti 膜打上來覆蓋 Scallop 側壁，因此第一階段孔底必須先沉積足夠厚的 Ti 薄膜。
- **核心物理解釋**：高製程壓力會增加氣相粒子碰撞機率，使靶材打出的中性 Ti 原子在靠近晶圓載盤（距靶材 $5\text{--}8\text{ cm}$）處大幅解離成 $\text{Ti}^+$ 離子（離子化比例從一般 DC 濺鍍的 $5\text{--}10\%$ 提升至高壓下的 $\sim 30\%$），進而受載盤上的 RF Bias 負電場垂直吸引、以小入射角深入孔底。

## 實驗設定與量化結果
- **測試試片**：AR 1.5（孔徑 $80\ \mu\text{m}$、深度 $120\ \mu\text{m}$，對應 MEMS 應用）與 AR 5.0（孔徑 $30\ \mu\text{m}$、深度 $150\ \mu\text{m}$，對應 2.5D Si Interposer 應用）。

| 製程參數 | AR 1.5 測試範圍與結果 | AR 5.0 測試範圍與結果 | 對覆蓋率與沉積速率的影響結論 |
| :--- | :--- | :--- | :--- |
| **製程壓力 (Pressure)** | $0.7 \to 15.0\text{ mTorr}$<br>B.S.C. **$19.4\% \to 52.1\%$**<br>速率 $2350 \to 1030\text{ \AA/min}$ | $1.4 \to 50.0\text{ mTorr}$<br>B.S.C. **$7.4\% \to 15.8\%$**<br>速率 $5040 \to 3165\text{ \AA/min}$ | **最大影響因子**：高壓提高 $\text{Ti}^+$ 離子化率、大幅提升 B.S.C.，但散射效應使沉積速率下降 |
| **載盤射頻偏壓 (RF Bias)** | $0\text{ W} \to 50\text{ W} \to 500\text{ W}$<br>B.S.C. $18.4\% \to 44.1\% \to 46.1\%$ | $0\text{ W} \to 200\text{ W} \to 600\text{ W}$<br>B.S.C. $3.7\% \to 9.2\% \to 10.2\%$ | **有加有效但快速飽和**：小功率偏壓即可吸引 $\text{Ti}^+$ 入孔，過高偏壓產生濺鍍蝕刻飽和 |
| **靶材直流功率 (DC Power)** | $3\text{ kW} \to 10\text{ kW}$<br>B.S.C. $25.0\% \to 15.6\%$（無顯著增益）<br>速率 $620 \to 2980\text{ \AA/min}$ | $5\text{ kW} \to 18\text{ kW}$<br>B.S.C. $16.3\% \to 12.4\%$<br>速率 $765 \to 3705\text{ \AA/min}$ | **主要影響沉積速率**：高功率（$18\text{ kW}$）反而壓抑載盤直流偏壓（$206\text{ V} \to 122\text{ V}$），略微降低 B.S.C. |

## 與現有 Wiki 的關聯與條件差異
- **前置製程銜接**：[[concept-step-coverage-tsv]] 與 [[compare-pcb-microvia-vs-3dic-tsv]] 說明此乾製程 PVD 覆蓋率如何決定後續濕製程電鍍填銅的良率。
- **量測限制提醒**：作者指出當低直流功率下孔底膜厚 $< 200\text{ \AA}$ 時，SEM 量測誤差會明顯放大（表 3-3 與 3-6 的低功率異常點），建議改用 TEM 量測。

## 待釐清問題與專題報告切入點
- 本研究未加入硬體輔助模組（IMP/Long Throw）做直接成本與良率對比，且未量測高 RF Bias 對 Ti 薄膜電阻率與內應力的影響；專題報告可將「壓力主導離子化 + RF Bias 導向」與濕製程的「對流主導 $\text{Cl}^-$ 吸附」並列對比。
