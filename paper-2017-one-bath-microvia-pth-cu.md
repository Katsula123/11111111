---
title: "Study of Microvia Filling and Plating Through Hole in One Copper Plating Bath"
authors: ["Chia-Fu Hsu (許家福)", "Wei-Ping Dow (竇維平)"]
year: 2017
venue: "國立中興大學化學工程學系博士論文"
tags: [microvia, pth, one-bath, dual-leveler, ntbc, abpv, taguchi, comsol]
status: read
raw_source: "RAW/NO.2 盲孔填充與通孔電鍍之同鍍槽電鍍技術之研究 - 許家福.pdf"
---

# 盲孔填充與通孔電鍍之同鍍槽電鍍技術 (2017)

## 給新手的背景脈絡（為什麼這篇重要？）
在傳統 HDI PCB 製程中，「盲孔填孔 (Microvia Filling)」與「通孔電鍍 (Plating Through Hole, PTH)」必須分開在兩個不同配方的電鍍槽進行：盲孔需要**高銅低酸**以確保孔底有足夠 $\text{Cu}^{2+}$ 進行孔底上移填充；通孔則需要**低銅高酸**來提高導電度、降低歐姆壓降，才能讓深孔中央與板面厚度一致（高均擲力 Throwing Power, TP）。本論文解決業界的核心痛點：**透過雙平整劑（NTBC + ABPV）搭配折衷酸銅比，在同一槽內同時完成高填孔率盲孔與高均擲力通孔。**

## 核心方法與理論推導
1. **電化學分析（CP 計時電位法 + CV 循環伏安法）**：
   - 利用工作電極轉速差（$100\text{ rpm}$ 模擬孔底弱對流 vs. $1000\text{ rpm}$ 模擬板面強對流）量測過電位差 $\Delta\eta = E_{100\text{rpm}} - E_{1000\text{rpm}}$，作為 [[concept-convection-dependent-adsorption]] (CDA) 強度的預測指標。
   - 針對高縱橫比通孔會消耗孔心 $\text{Cu}^{2+}$（$0.24\text{ M} \to 0.20\text{ M}$），修正 CP 判準為 $\Delta\gamma = E_{100\text{rpm}, 0.20\text{M}} - E_{1000\text{rpm}, 0.24\text{M}}$。
2. **雙平整劑協同機制**：
   - 單純 `PEG-Cl-SPS` 三劑無顯著 CDA 效應（$\Delta\eta = 0\text{ mV}$）；加入 `1 ppm NTBC + 1 ppm ABPV` 後 $\Delta\eta$ 躍升至 $25\text{ mV}$。
   - **NTBC** 會發生電化學開環消耗，單用易形成 W 型輪廓與孔底凸起；**ABPV** 不易消耗但藉靜電吸引修飾輪廓，兩者併用可實現平坦的平台式上移填充。
3. **COMSOL 模擬與田口實驗 ($L_9(3^4)$)**：
   - 盲孔建立流速與等效轉速關係 $V_r = 0.5\omega^{3/2}\nu^{-1/2}r Y_h$，定義對流強度比值 $m = V_{\max}/Y_h$，證明板面與孔底的對流強度差 $\Delta m$ 主導填充速率（Specific Filling Fraction, $\text{FF} = A_i/A_t$）。
   - 通孔模擬比較「陰極旋轉」與「空氣曝氣攪拌」，證實曝氣因兩側氣泡時間差產生週期性反轉軸向流，使孔內外覆蓋率差異極小（$\Delta\theta \approx 0.08$），優於兩側等壓無對流的陰極旋轉。

## 實驗設定與量化結果
- **測試試片**：盲孔（孔徑 $95\ \mu\text{m}$、$115\ \mu\text{m}$，孔深 $85\ \mu\text{m}$）；通孔（孔徑 $250\ \mu\text{m}$，孔深 $1500\text{--}1600\ \mu\text{m}$）。

| 配方／製程情境 | 酸銅組成（含 $60\text{ ppm Cl}^- + 200\text{ ppm PEG}$） | 關鍵添加劑與電流密度 | 盲孔填孔率 (FP) | 通孔均擲力 (TP) | ANOVA 主要貢獻因子 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **純盲孔最佳化** | $0.88\text{ M CuSO}_4 + 0.54\text{ M H}_2\text{SO}_4$ | $1\text{ ppm NTBC}, 2\text{ ppm ABPV}, 2\text{ ppm SPS}, 1.62\text{ A/dm}^2$ | **$97\%$** | $60\%$（直接套用於通孔） | NTBC ($38.61\%$) > SPS ($26.86\%$) ≈ $J$ ($26.86\%$) |
| **純通孔最佳化** | $0.24\text{ M CuSO}_4 + 1.88\text{ M H}_2\text{SO}_4$ | $1\text{ ppm NTBC}, 1\text{ ppm ABPV}, 1\text{ ppm SPS}, 1.29\text{ A/dm}^2$ | $10\%$（直接套用於盲孔） | **$104\%$** | $J$ ($70.96\%$) > SPS ($22.46\%$) |
| **同鍍槽同步電鍍** | $0.72\text{ M CuSO}_4 + 1.32\text{ M H}_2\text{SO}_4$ | $1\text{ ppm NTBC}, 1\text{ ppm ABPV}, 1.5\text{ ppm SPS}, 1.29\text{ A/dm}^2$ ($90\text{ min}$) | **$90\%$** ($\phi 95\ \mu\text{m}$)<br>$75\%$ ($\phi 115\ \mu\text{m}$) | **$83\%$** | 兼顧 $\text{Cu}^{2+}$ 補充、導電度與 SPS 競爭吸附 |

## 與現有 Wiki 的關聯與條件差異
- **承接前作**：[[paper-2011-forced-convection-microvia-cu]] 只分析無添加劑的純流場；本論文補齊添加劑電化學與反應動力學，並將「孔底與板面的對流強度差 $\Delta m$」確立為填孔速率的定量指標。
- **條件差異**：[[compare-microvia-vs-pth-plating]] 詳細整理盲孔與通孔在酸銅比、攪拌方式與主導因子的衝突與折衷。

## 待釐清問題與專題報告切入點
- 專題報告可重點展示「為何單純盲孔配方做通孔會失敗（TP 僅 $60\%$）、單純通孔配方做盲孔會失敗（FP 僅 $10\%$）」，進而引出雙平整劑與折衷酸銅比的工程解法。
