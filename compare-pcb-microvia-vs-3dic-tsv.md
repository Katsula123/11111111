# PCB 微盲孔濕製程電鍍 vs. 3D-IC TSV 乾製程濺鍍比較

> 本頁串接 [[paper-2011-forced-convection-microvia-cu]]、[[paper-2017-one-bath-microvia-pth-cu]] 與 [[paper-2012-tsv-ti-sputtering-coverage]]，對比不同尺度互連結構在「將材料送進深孔底部」上的物理機制差異。

| 比較維度 | PCB 微盲孔／通孔（濕製程電鍍銅） | 3D-IC TSV（乾製程 PVD 濺鍍 Ti 阻隔層） |
| :--- | :--- | :--- |
| **製程階段與目的** | 電鍍填充導體（填實盲孔或均勻鍍覆通孔壁） | 電鍍前的前置成膜（阻隔層／種子層） |
| **典型尺寸與深寬比** | 盲孔 $\phi 60\text{--}120\ \mu\text{m}$（$\text{AR} \approx 0.5\text{--}2.0$）；通孔 $\text{AR} \approx 6.4$ | AR $1.5$（$80\ \mu\text{m} \times 120\ \mu\text{m}$）至 AR $5.0$（$30\ \mu\text{m} \times 150\ \mu\text{m}$） |
| **孔底輸送瓶頸** | 孔壁黏滯力阻礙流體對流（$\text{AR} \ge 1.2$ 渦流進不去），且陰極排斥負電 $\text{Cl}^-$ | 中性原子直線飛行，大入射角被孔口與 Bosch Scallop 側壁遮蔽 |
| **核心驅動／調控手段** | 強制對流（曝氣攪拌）＋ 化學添加劑競爭吸附（PEG / Cl⁻ / SPS / NTBC / ABPV） | **製程壓力**提升氣相碰撞離子化率（$\text{Ti}^+ \sim 30\%$）＋ **載盤 RF Bias** 垂直吸引 |
| **過高參數的副作用** | 流速 $> 0.09\text{ m/s}$ 增益遞減；SPS 過量 ($1.5\text{ ppm}$) 導致孔口加速封死產生 Void | DC Power 過高 ($18\text{ kW}$) 壓抑載盤偏壓；RF Bias 過高使濺鍍蝕刻飽和 |
