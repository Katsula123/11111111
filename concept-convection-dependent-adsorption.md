# 對流性吸附機構 (Convection-Dependent Adsorption, CDA)

## 核心定義（給新手的白話理解）
在銅電鍍液中，抑制劑聚乙二醇 (Polyethylene Glycol, PEG) 必須靠**氯離子 ($\text{Cl}^-$) 作為橋樑**才能吸附在陰極銅表面形成阻擋膜。但 $\text{Cl}^-$ 帶負電，會被帶負電的陰極排斥而容易脫附；因此需要靠**電解液的強制對流**提供足夠動能，把 $\text{Cl}^-$ 推向陰極。

這導致在同一個盲孔內產生兩種截然不同的微環境：
- **板面與孔口（強對流區）**：$\text{Cl}^-$ 容易補充並吸附 → 促進 PEG 與平整劑吸附 → **銅沉積被強烈抑制**。
- **孔底與角落（弱對流區）**：$\text{Cl}^-$ 難以補充且易脫附 → 加速劑 SPS/MPS 佔據優勢 → **銅沉積大幅加速**。

## 在 Wiki 中的實證與演進
- **純流場質傳驗證**：[[paper-2011-forced-convection-microvia-cu]] 用 COMSOL 證實當盲孔縱橫比 $\text{AR} \ge 1.25$ 時，孔底與孔外的 $\text{Cl}^-$ 通量比會掉到 $< 0.001$，形成天然的濃度梯度。
- **對流強度差量化與雙平整劑**：[[paper-2017-one-bath-microvia-pth-cu]] 指出單純 `PEG-Cl-SPS` 的 CDA 電位差極小（$\Delta\eta = 0\text{ mV}$），必須加入平整劑（如 `NTBC + ABPV`）才能把 CDA 效應放大至 $\Delta\eta = 25\text{ mV}$；並證明板面與孔底的對流強度差 $\Delta m = m_{\text{surface}} - m_{\text{bottom}}$ 直接主導填孔速率。
