# Actions運用

Org設定: すべてのRepositoryでActions有効、許可Actionsをselectedに制限。許可一覧は `actions/checkout@*`, `withastro/action@*`, `actions/deploy-pages@*`。Default `GITHUB_TOKEN` permissionsはread、PR review承認権限なし。Org sha pinningは未有効。既存の追加Public repo `Site` がmutable action tagsを使うため、allowlistに必要な公式actionsを残しています。

4つの親repoに週次/手動Submodule更新PR workflowを追加しました。workflow本文では外部Actionを呼びません。標準Ubuntu、5分timeout、必要なcontents/pull-requests write、concurrency制御、LFS smudge skipを設定。設定は各PRがmainへマージされて初めて有効になります。初回workflow_dispatchの認証・PR作成は各リポジトリで実行確認が必要です。

依存先変更は親repoへのbot PRで伝播し、mainへの直接push/自動mergeを行いません。
