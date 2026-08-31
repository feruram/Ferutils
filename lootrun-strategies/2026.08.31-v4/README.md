# Ferutils Lootrun Strategy 2026.08.31 v4

Ferutils 0.8.x 用の独立配布Lootrunストラテジーです。

## 収録ファイル

- `ferutils-lootrun-strategy-2026.08.31-v4.toml`: ストラテジー本体

## 導入方法

1. Ferutils Appを終了します。
2. 現在使用している `lootrun-strategy.toml` をバックアップします。
3. Ferutils Appの `Settings` → `Lootrun strategy` から同梱TOMLを選択します。
4. 設定を保存してFerutils Appを再起動します。

## 互換性

- Strategy schema: 3
- Tested with Ferutils App 0.8.1–0.8.3 strategy evaluator

## 方針

- 通常時のBlue過剰推薦を抑制
- Red・White・Orange・Crimsonなど、一回性・期限・継続性に関わるBeaconをMission Objectiveより優先
- 残ChallengeとOrange残回数に応じてAquaによる延長準備を実施
- Greyの出現率低下前にMission候補を確保
- Gambling Beastは対応Missionが不足している場合に抑制
- Boon/Curseの安全判定には個数ではなくPotencyを使用

このストラテジーは将来のFerutils本体リリースとは別の
`lootrun-strategy-v*` リリース系列で更新されます。

