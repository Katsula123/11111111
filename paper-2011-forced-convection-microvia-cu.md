---
title: "Study the Effect of Forced Convection on Micro Via Filling Process for Electroplating Copper"
authors: ["Chia-Fu Hsu (許家福)", "Shueiwan H. Juang (莊水旺)"]
year: 2011
venue: "國立臺灣海洋大學機械與機電工程學系碩士論文"
tags: [microvia, forced-convection, comsol, cda, copper-electroplating]
status: read
raw_source: "RAW/NO.1 000101 強迫對流效應對微米級填孔電鍍銅製程的影響.pdf"
---

# 強迫對流對微米級盲孔電鍍銅質傳之影響 (2011)

## 給新手的背景脈絡（為什麼這篇重要？）
在高密度互連 (High Density Interconnection, HDI) 印刷電路板中，層與層之間需要靠微米級盲孔 (Microvia) 填滿銅來導通訊號與電力。如果電鍍時孔口銅長得比孔底快，就會把孔口封死並在內部留下致命的空洞 (Void)。過去奈米級晶圓製程多假設流體進不去深孔、只靠自然擴散；但 PCB 盲孔尺寸在數十到百微米等級，本論文用數值模擬回答一個基礎問題：**「把電解液流速加快（強制對流），到底能不能把 $\text{Cu}^{2+}$ 與 $\text{Cl}^-$ 送進盲孔底部？」**

## 核心方法與理論推導
- **理論基礎**：採用竇維平 (W. P. Dow) 提出的 [[concept-convection-dependent-adsorption]] (CDA)，假設 $\text{Cl}^-$ 覆蓋率決定抑制劑 PEG 與加速劑 SPS 的局部吸附，進而實現 [[concept-bottom-up-superfilling]]。
- **COMSOL 2D 穩態層流耦合模型**：
  1. **流場（不可壓縮 Navier-Stokes）**：$\rho (\mathbf{u} \cdot \nabla \mathbf{u}) = \nabla \cdot [-p\mathbf{I} + \eta (\nabla \mathbf{u} + (\nabla \mathbf{u})^T)] + \mathbf{B}$
  2. **質傳（Nernst-Planck）**：$\frac{\partial c_i}{\partial t} + \nabla \cdot (-D_i \nabla c_i - z_i u_{mi} F c_i \nabla V + c_i \mathbf{u}) = R_i$
  3. **陰極電流密度（Butler-Volmer）**：$i = \frac{C_{\text{Cu}^{2+}}}{C_{\text{Cu}^{2+}}^0} \sum z i_0 \left\{ \exp\left[-\frac{\alpha F \eta}{RT}\right] - \exp\left[\frac{(1-\alpha)F\eta}{RT}\right] \right\}$
- **簡化假設**：未求解移動邊界沉積輪廓，亦未納入 PEG/SPS 化學交互反應，專注分析純流場對離子濃度通量（Flux）的物理極限。

## 實驗設定與量化結果
- **基礎模擬條件**：$C_{\text{Cu}^{2+}}^{bulk} = 880\text{ mol/m}^3$、$C_{\text{Cl}^-}^{bulk} = 1.69\text{ mol/m}^3$、$T = 301\text{ K}$、過電位 $\eta = -0.25\text{ V}$、$i_0 = 194\text{ A/m}^2$。
- **掃描變數**：入口流速 $0.03, 0.06, 0.09, 0.12\text{ m/s}$；孔徑 $D = 60, 80, 100, 120\ \mu\text{m}$；孔深 $h = 60, 80, 100, 120\ \mu\text{m}$；側壁角度 $90^\circ$（垂直）vs. $95^\circ$（傾斜 $5^\circ$）。

| 探討維度 | 測試條件 | 關鍵量化結果 | 物理機制解釋 |
| :--- | :--- | :--- | :--- |
| **縱橫比 (AR) 極限** | $\text{AR} \ge 1.2$（如 $D=60\ \mu\text{m}, h \ge 80\ \mu\text{m}$） | 孔底／孔外 $\text{Cu}^{2+}$ 通量比 $< 0.1$；$\text{AR} \ge 1.25$ 時 $\text{Cl}^-$ 通量比 $< 0.001$ | 流體慣性力無法克服黏滯力，渦流無法觸及孔底，孔底退回純擴散與電遷移 |
| **流速增益遞減** | 流速 $0.03 \to 0.12\text{ m/s}$ | 孔外 $\text{Cl}^-$ 通量在 $0.03 \to 0.06\text{ m/s}$ 增 $29.32\%$，但在 $0.09 \to 0.12\text{ m/s}$ 僅增 $12.96\%$ | 對流推力與陰極對 $\text{Cl}^-$ 的靜電排斥力趨於平衡 |
| **左右側壁不對稱** | 垂直盲孔側壁 | 右端側壁 $\text{Cu}^{2+}$ 通量比左端高 $15\text{--}23\%$；$\text{Cl}^-$ 左右差異達 $2$ 倍以上 | 流體沖擊下游（右端）孔口側壁，加大孔徑可改善 $\text{Cu}^{2+}$ 差異但無法改善 $\text{Cl}^-$ |
| **側壁傾斜 $5^\circ$** | $95^\circ$ 傾斜開口 | 孔底 $\text{Cu}^{2+}$ 與 $\text{Cl}^-$ 通量反而**降低 $5\text{--}10\%$** | 傾斜壁面削弱孔內渦流往孔底的正向傳遞，僅微調孔口側壁 $\text{Cu}^{2+}$（右降 $2\%$、左升 $3\text{--}5\%$） |

## 與現有 Wiki 的關聯與條件差異
- **延伸發展**：[[paper-2017-one-bath-microvia-pth-cu]] 為同一作者後續的博士論文，從本篇的「無添加劑反應流場模擬」進一步推進到「雙平整劑電化學動力學＋實際盲孔／通孔同鍍槽電鍍」。
- **跨領域對比**：[[compare-pcb-microvia-vs-3dic-tsv]] 說明 PCB 微盲孔濕製程與 3D-IC TSV 乾製程在高深寬比傳遞瓶頸上的異同。

## 待釐清問題與專題報告切入點
- 本模型未考慮電極表面沉積移動邊界與 PEG/SPS 消耗反應，適合在專題報告中作為「為何單靠物理攪拌無法解決高縱橫比填孔、必須引入有機添加劑」的流體力學佐證。
