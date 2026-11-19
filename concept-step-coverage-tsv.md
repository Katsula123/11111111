# TSV 階梯覆蓋率與 Bosch Scallop 效應 (Step Coverage in TSV)

## 核心定義
在 3D-IC 直通矽晶穿孔 (Through-Silicon Via, TSV) 進行電鍍填銅前，必須先以 PVD 濺鍍阻隔層（如 Ti）與種子層（如 Cu）。**底部階梯覆蓋率 (Bottom Step Coverage, B.S.C.)** 定義為孔底膜厚 $b$ 與晶圓平面膜厚 $t$ 的比值：
$$\text{B.S.C.} = \frac{b}{t} \times 100\%$$

## 為何 TSV 很難鍍均勻？
1. **直線飛行限制 (Line of Sight)**：傳統 PVD 濺鍍粒子多為不帶電的中性原子，從靶材往各方向直線飛行，大入射角粒子會被擋在孔口，難以進入深孔。
2. **Bosch 扇貝側壁 (Scallop Sidewall)**：矽深蝕刻常採用 Bosch 製程，會在側壁留下波浪狀扇貝凹陷，凹陷上半部處於粒子飛行的陰影區，極易造成薄膜不連續。
3. **兩階段反濺鍍解法 (2-Step Sputter + Re-sputtering)**：第一階段先在孔底沉積足夠厚的金屬膜；第二階段提高載盤 RF Bias，利用離子轟擊將孔底既有的金屬膜重新濺鍍到 Scallop 側壁上。

## Wiki 相關論文
- [[paper-2012-tsv-ti-sputtering-coverage]]（驗證提高製程壓力可提升 $\text{Ti}^+$ 離子化率至 $\sim 30\%$，搭配適量 RF Bias 即可在不改裝機台硬體下提升 B.S.C.）
