# Git LFS

`Game-001-Art/.gitattributes` はBLEND/FBX/PSD/SPP/EXR/TIF/TIFF/WAV/AIF/AIFF/MOV/MP4をLFS対象にします。大きなテストファイルやLFS payloadは送っていません。

GitHub公式情報ではFree for OrganizationsにLFS storage/bandwidth各10 GiBが含まれ、予算を$0に設定すると超過分は課金されず当月のLFS利用が停止します。今回GitHub Billing APIで `git_lfs` 組織予算$0、`prevent_further_usage=true` を確認しました。2026年usage summaryにはLFS利用項目なし。制作元を含むrecursive cloneはLFS smudgeを避けてください。
