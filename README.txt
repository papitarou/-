# がんばり☆きろく帳（PWA 版）

このフォルダをそのまま Web にアップすれば、iPhone で「ホーム画面に追加」→ アプリのように使えます。

## ファイル一覧
- index.html … アプリ本体
- manifest.json … アプリアイコン/名前設定
- service-worker.js … オフライン対応
- icon-192.png, icon-512.png … アイコン

## 使い方（GitHub Pages の例）
1. GitHubで新しいリポジトリを作る（PublicでOK）
2. このフォルダ内のファイルをすべてアップロード（ドラッグ&ドロップでOK）
3. リポジトリの「Settings」→「Pages」→「Branch」を `main` / `/root` にして保存 → URLが発行される
4. iPhoneのSafariでそのURLを開く → 共有ボタン → 「ホーム画面に追加」

## セキュリティの考え方
- 記録データは**端末内（localStorage）だけ**に保存。サーバーへ送信しません。
- HTTPSで配信されると、安全に読み込めます（GitHub Pages は自動でHTTPS）。
- 外部スクリプトは使わず、CSP（Content-Security-Policy）を設定済み。

## よくある質問
- **オフラインでも動く？** … はい。初回アクセス後は、オフラインでも起動・表示できます。
- **データの引き継ぎは？** … 端末ごとに保存されます。機種変更時はJSON書き出し→新端末で読み込み機能を今後追加予定です。
