# 検証結果 (2026-11-27)

## 実測PASS
- `gh auth status`: fureq-dev active、repo/project/admin:org/workflow scopesあり。
- 14初期repo + 既存SiteのPublic visibilityをREST APIで確認。
- 既存9 TeamsのVisible状態/親子関係、default repo permission none。
- team-repository grantsは既存なしから目標14 Write grantsを設定。
- 14 main branch protections: 1 approval、stale review dismissal、admins enforce、force push/deletion false。CI checkは未設定。
- 4 GitHub Projects Public、各Status 7 options、Priority/Team/Role/Task Type/Target Version/Start Date/Due Date、Assignees/Milestone built-ins。Repositories/Teams linked。
- 12 direct submodule gitlinks + nested RenderingLibraryをローカルcloneで検査。`git ls-files -s` のmode 160000、remote main上にcommit存在。HTTPS `.gitmodules`。
- Billing budgets: Actions, Git LFS, Packages, Codespaces all $0 with prevent_further_usage true。Actions current-year usage is discounted to $0 net. LFS payload転送なし。

## PR待ち
- docs/templates/CODEOWNERS/LFS/workflows/submodule content is pushed to 14 review branches and open PRs. GitHub `main`に未反映のため、clone/fetch test must be repeated after merge.

## 未検証
- 14 PR内容の最終レビュー・承認・merge。
- Actions workflow execution (including public-child/no-token-url behavior, no-change path, duplicate PR path, and update propagation).
- Actual GitHub Desktop UI, non-owner member access, Git LFS payload, Project filters on populated items, and Issue Forms rendered UI.
- Free quota remaining amounts are not present in the checked budget/usage response. No over-quota load was sent.

## 既知の制約
- GitHub Free requires public-repo branch protection; all repositories are public by explicit user instruction. Do not store secrets, personal data, unlicensed assets, or confidential project info.
- Site has an existing workflow with mutable official action tags; org SHA pinning remains disabled.
- Project-specific detailed views depend on task type/role fields and labels being maintained as issues are added. Empty Projects currently contain no task evidence.
