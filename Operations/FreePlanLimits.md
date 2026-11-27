# 無料プラン制約と確認結果

GitHub Free for Organizationsを維持し、有料プラン変更は行っていません。2026-11-27にOrganization billing budgetsを確認し、Actions、Git LFS、Packages、Codespacesがそれぞれ $0 / `prevent_further_usage=true` でした。Actions usage summaryではLinux runner 24分、net amount $0、storage 0.0133 GB-hours、net amount $0。LFSの2026 usage itemはありません。

標準GitHub-hosted runnerのみを使い、初期Submodule workflowは週1回または手動、timeout 5分、artifact/cacheなし。予算が$0のため無料枠超過時は各製品が停止する前提です。GitHubが公開しているFree LFS quotaはstorage/bandwidth各10 GiB。

Billing endpointは現在 `/organizations/{org}/settings/billing/...`。旧 `/orgs/{org}/settings/billing/actions` はHTTP 410で移行済み。
