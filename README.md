
# セール施策の因果効果分析（DID法）

本プロジェクトは、アパレルECにおけるセール施策の因果効果を定量的に評価するための仮想データ分析です。差分の差分法（Difference-in-Differences, DID）を用いて、セールが売上・販売点数・利益・利益率に与える影響を分析しました。

## プロジェクト構成

```
.
├── analysis.ipynb  # 実行可能なNotebook
├── results/
│   ├── did_result_sales.txt              # 各指標に対するDIDの回帰結果
│   ├── did_result_units.txt
│   ├── did_result_profit.txt
│   └── did_result_profit_rate.txt
├── figures/
│   ├── sales_did_plot.png                # 各指標の可視化結果（Before/After × Control/Treatment）
│   ├── units_did_plot.png
│   ├── profit_did_plot.png
```

## 分析手法と指標

- **分析手法**：差分の差分法（DID）
- **対象指標**：
  - `sales`（売上）
  - `units`（販売点数）
  - `profit`（利益）
  - `profit_rate`（利益率）

## 分析の流れ

1. 仮想データを生成（100商品・60日間）
2. セールの有無（Treatment）とBefore/Afterを組み合わせたデータ構造を作成
3. 指標ごとの平均値を可視化（棒グラフ）
4. 回帰分析によりセールの効果を数値的に評価

## 主な結果と考察

- `treatment:post`の係数が統計的に有意であることが確認され、セール施策がポジティブな効果（売上や利益の増加）を持つことが示唆されました。
- 仮想データにおいては、セール実施が全体的に収益性の向上に寄与していると解釈されます。

## 注意点

- 本分析はシミュレーションベースであり、実データに基づいた分析ではありません。
- グループ間でのバイアス（例：単価の違い）が存在する場合、因果推論としての前提が崩れる可能性がある点に留意が必要です。

## 実行方法

Python環境にて `analysis.ipynb` を開き、セルを上から順に実行してください。必要なディレクトリはNotebook内で自動生成されます。

---

開発者: 物理学専攻M1（インターン応募用に作成）
