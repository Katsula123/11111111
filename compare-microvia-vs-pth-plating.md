# 盲孔填孔 (Microvia) vs. 通孔電鍍 (PTH) 與同鍍槽比較

> 本頁彙整 [[paper-2011-forced-convection-microvia-cu]] 與 [[paper-2017-one-bath-microvia-pth-cu]] 之條件與結果，供專題報告對比使用。

## 製程目標與配方衝突

| 比較維度 | 盲孔填孔 (Microvia Filling) | 通孔電鍍 (PTH) | 同鍍槽同步電鍍 (One-Bath) |
| :--- | :--- | :--- | :--- |
| **幾何特徵** | 單端封閉盲孔（如 $\phi 95\ \mu\text{m} \times 85\ \mu\text{m}$） | 雙端貫穿通孔（如 $\phi 250\ \mu\text{m} \times 1500\text{--}1600\ \mu\text{m}$） | 兩者共存於同一板面 |
| **核心品質指標** | 填孔率 $\text{FP} = H_2/H_1$（目標無空洞填滿） | 均擲力 $\text{TP} = \frac{(C_1+C_2)/2}{(H_1+H_2+H_3+H_4)/4}$（目標全孔均勻） | 同時兼顧高 FP 與高 TP |
| **酸銅比需求** | **高銅低酸**（$0.88\text{ M CuSO}_4 + 0.54\text{ M H}_2\text{SO}_4$）<br>確保孔底供銅與板面過電位差 | **低銅高酸**（$0.24\text{ M CuSO}_4 + 1.88\text{ M H}_2\text{SO}_4$）<br>提高導電度、降低歐姆壓降 | **折衷酸銅比**（$0.72\text{ M CuSO}_4 + 1.32\text{ M H}_2\text{SO}_4$） |
| **主要影響因子 (ANOVA)** | **NTBC ($38.61\%$)** > SPS ($26.86\%$) ≈ 電流密度 ($26.86\%$) | **電流密度 ($70.96\%$)** > SPS ($22.46\%$) | 需微調 SPS ($1.5\text{ ppm}$) 與低電流密度 ($1.29\text{ A/dm}^2$) |
| **單獨配方交叉套用後果** | 用純通孔配方鍍盲孔 → **FP 僅 $10\%$** | 用純盲孔配方鍍通孔 → **TP 僅 $60\%$** | 同步達成 **FP $= 90\%$ ($\phi 95\ \mu\text{m}$)、TP $= 83\%$** |

> [條件差異] 攪拌流場對兩者的影響機制不同：在盲孔中，對流強弱差 $\Delta m$ 驅動孔底上移（[[paper-2011-forced-convection-microvia-cu]] 指出 $\text{AR} \ge 1.2$ 時對流進不了孔底）；在通孔中，陰極旋轉因兩側等壓無法產生孔內軸向流，必須使用**空氣曝氣攪拌**製造週期性反轉軸向流，才能把孔心覆蓋率差異壓低至 $\Delta\theta \approx 0.08$（[[paper-2017-one-bath-microvia-pth-cu]]）。
