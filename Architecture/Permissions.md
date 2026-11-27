# アクセス権限

Organization default repository permissionは `none`。すべてPublicなので誰でもread可能ですが、writeは担当Teamに限定します。既存9 TeamsのVisible状態を維持。親子継承はGitHubのTeam hierarchyに従います。

| Repository | Write担当 | 備考 |
|---|---|---|
| `.github`, `.github-private`, `DevelopmentDocs`, `DevelopmentTools` | Shared-Services | `.github-private`もPublic |
| `RenderingLibrary`, `RenderingWorkspace` | Rendering-Team | 描画班 |
| `GameEngine`, `EngineEditor`, `EngineHub`, `EngineWorkspace` | Engine-Team | エンジン班 |
| `Game-001` | Game-001-Team | 統合リポジトリ |
| `Game-001-Code` | Game-001-Programmers | コード担当 |
| `Game-001-Art` | Game-001-Artists | アート担当 |
| `Game-001-Design` | Game-001-Planners | 企画担当 |

全15 repo中、今回の14 repoで上記14 Write grantsを確認。既存 `Site` は初期14 repoの対象外。Team membership、Owner権限、管理者Writeは変更していません。公開repoのため職種を問わずreadできます。公開内容に秘密情報/個人情報/未許諾素材を含めないでください。