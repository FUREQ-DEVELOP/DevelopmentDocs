# セットアップ進捗

更新日: 2026-11-27 (JST)
現在: PHASE 13 — `IN_PROGRESS`（全PRレビュー・マージと実メンバー確認待ち）

## 完了した実設定
- PHASE 01: GitHub Freeを維持。Org default permission `none`、Actions allowlistを設定。Default workflow token permissionはread、PRレビュー承認不可。SHA pinningは既存 `Site` のtag参照と整合しないため未有効。
- PHASE 02: 既存9 Teamsを再利用。可視性は `closed` (Visible)、階層を確認。メンバー構成は変更していない。
- PHASE 03: 初期14リポジトリを再利用。全てPublic、main/Issuesを確認。既存 `Site` も含む全15 repoがPublic。Description/topics、squash-only、merge後branch削除を設定。
- PHASE 04: 確認済みの14 team-repository Write grantを設定。Repo default permissionはnone。
- PHASE 08: 14 repoのmainに1承認PRレビュー、古いレビューdismiss、admin適用、force push/deletion禁止。存在しないCI checkは必須にしていない。
- PHASE 09: 公開Organization Projects 4件、各共通field、Status/ Priority選択肢、repos/teams連携、複数viewを設定。
- 請求対策: Actions/LFS/Packages/Codespaces全て$0 budgetと超過時停止をBilling APIで確認。LFS大容量転送なし。

## PRで構築中 (mainには未反映)
- PHASE 05: 12 direct SubmoduleをPRに登録。GameEngine PRにはnested RenderingLibraryを登録。全gitlink mode 160000、各SHAはchild remote mainで確認。Game-001の未認証recursive cloneではdirect 5件を取得できたが、nested RenderingLibraryはGameEngineの新gitlinkがまだ親repoに取り込まれていないため未取得。GameEngine PR merge後に親workflowを手動実行し、更新PRを作って伝播させる。
- PHASE 06: RenderingWorkspace, GameEngine, EngineWorkspace, Game-001に更新PR workflow。
- PHASE 07: Game-001-Art LFS/ignore設定。
- PHASE 08: CODEOWNERS、PR運用テンプレート、Gitルール。
- PHASE 10: 共通および担当領域Issue Forms、PR template。
- PHASE 11: 公開プロフィールと共同開発リンク集。`.github-private` は指示どおりPublicで、名前に反して公開入口として運用。
- PHASE 12: 日本語の職種別/管理者向けマニュアル一式。

## PR一覧
- [.github #1](https://github.com/FUREQ-DEVELOP/.github/pull/1)
- [.github-private #1](https://github.com/FUREQ-DEVELOP/.github-private/pull/1)
- [DevelopmentDocs #1](https://github.com/FUREQ-DEVELOP/DevelopmentDocs/pull/1)
- [DevelopmentTools #1](https://github.com/FUREQ-DEVELOP/DevelopmentTools/pull/1)
- [RenderingLibrary #1](https://github.com/FUREQ-DEVELOP/RenderingLibrary/pull/1)
- [RenderingWorkspace #1](https://github.com/FUREQ-DEVELOP/RenderingWorkspace/pull/1)
- [GameEngine #1](https://github.com/FUREQ-DEVELOP/GameEngine/pull/1)
- [EngineEditor #1](https://github.com/FUREQ-DEVELOP/EngineEditor/pull/1)
- [EngineHub #1](https://github.com/FUREQ-DEVELOP/EngineHub/pull/1)
- [EngineWorkspace #1](https://github.com/FUREQ-DEVELOP/EngineWorkspace/pull/1)
- [Game-001 #1](https://github.com/FUREQ-DEVELOP/Game-001/pull/1)
- [Game-001-Art #1](https://github.com/FUREQ-DEVELOP/Game-001-Art/pull/1)
- [Game-001-Code #1](https://github.com/FUREQ-DEVELOP/Game-001-Code/pull/1)
- [Game-001-Design #1](https://github.com/FUREQ-DEVELOP/Game-001-Design/pull/1)

## 未完了・要確認
- 14 PRの公開内容とdiffを人間がレビュー・承認し、branch protection経由でmergeする。認証ユーザー自身で承認/迂回していない。
- Merge後、GitHub ActionsでSubmodule clean clone、`workflow_dispatch`、重複PR防止/更新伝播を実行検証する。
- GitHub Desktopの実アプリから取得するUI試験、および一般メンバー権限によるclone/PR試験は未実施。手順はマニュアルに記載。
- Projectの空状態、公開設定、14 repo/9 team Master Roadmap連携、担当Project link、fieldsとviewsを確認。実taskがないため絞り込み結果は未検証。
- 101個のIssue Forms YAMLと4 workflow YAMLをPyYAMLでparseし、必要key/field/type/idを構造検査、エラー0。ブラウザ上のフォーム描画確認は未実施。
- `Site` は初期14 repoの対象外。公開状態以外のtopics/branch rules/workflowは変更していない。
- 無料枠残量を超えるビルドやLFS通信は実行していない。

## 次の作業
1. 14 PRのdiffを確認してレビュー承認・merge。
2. Submodule親をclean cloneしてrecursive取得とLFS smudge抑止を確認。
3. 4更新workflowを手動実行し、差分なし/差分あり/既存PR更新を検証。
4. フォームとProjectsビューをテストIssueで確認する場合は不要な公開Issueを残さず終了処理する。
5. PHASE 13を完了判定し、依頼範囲外の製品コード実装は開始しない。
