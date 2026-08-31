# Lootrun strategy releases

Ferutils本体とLootrunストラテジーは同じGitHub repositoryで配布しますが、
リリース系列と成果物を分離します。

## Release naming

- App/Mod: `v0.x.y` / `Ferutils 0.x.y`
- Strategy: `lootrun-strategy-vYYYY.MM.DD.N` / `Ferutils Lootrun Strategy YYYY.MM.DD vN`

Strategy releaseをGitHubのLatest releaseには指定しません。これにより、
Ferutils App利用者に表示されるLatestは引き続きApp/Mod本体になります。

## Assets

各Strategy releaseには次の3ファイルを添付します。

1. `ferutils-lootrun-strategy-YYYY.MM.DD-vN.toml`
2. `Ferutils-Lootrun-Strategy-YYYY.MM.DD-vN.zip`
3. `SHA256SUMS-lootrun-strategy.txt`

ZIPの内部は同名の専用フォルダにまとめ、READMEとTOMLを収録します。

## Source workspace

検証済みの原本はLootrunSimulatorの `strategy/` に保存し、公開用成果物は
`release/lootrun-strategy/<version>/` に生成します。Ferutils本体のビルド成果物とは
混在させません。

