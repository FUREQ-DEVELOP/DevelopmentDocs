# Submodule workflow

Clone後は `git submodule update --init --recursive`。親の更新は `git submodule update --remote <path>` で確認し、gitlinkの差分をPRに含めます。`.gitmodules`のHTTPS URLと160000 modeを確認します。GitHub Desktopでは必要に応じてGit Bashを使います。
