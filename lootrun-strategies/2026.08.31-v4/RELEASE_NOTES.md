# Ferutils Lootrun Strategy 2026.08.31 v4

Ferutils本体とは独立したLootrunストラテジーの初回リリースです。

## 主な変更

- 序盤の通常Blueを降格し、明確な安全上の必要性または高Potency時のみ優先
- 残Challengeが少ない場合のRedとAqua延長準備を強化
- Power 3 Whiteと失効直前OrangeをMission Objectiveより優先
- Challenge 20以降の初回Crimsonと、第2Trial構築を強化
- 高タイマー時に時間が上限で無駄になるGreen Objectiveを抑制
- Porphyrophobia、Lights Out、Gambling Beastなどの組み合わせ判定を改善
- Chronotrigger完了後もGreenの時間補正を維持

## 検証

同一100シードのBALANCED検証では、旧guide-expanded-v3比で次の変化を確認しました。

- 平均Effective Pull: 313.88 → 343.66
- 平均Flying Chest: 24.42 → 29.05
- 平均Mission: 2.74 → 3.20
- 平均Trial: 1.38 → 1.55
- 3 Mission・2 Trial以上: 38% → 52%
- 100 Challenge到達: 52% → 47%

純粋な100 Challenge到達率よりも、Mission・Trial構築と総合報酬を重視した版です。

## Assets

- `ferutils-lootrun-strategy-2026.08.31-v4.toml`: 直接読み込み用
- `Ferutils-Lootrun-Strategy-2026.08.31-v4.zip`: READMEを含む独立フォルダ版
- `SHA256SUMS-lootrun-strategy.txt`: ダウンロード検証用

