# Chapter.03: Linux の運用 / 保守

{docsify-updated}

###### tags: `.AWS`, `.Introduction`, `.Book`, `.Tech`

---

## 3.1: SSH 接続

- サーバーソフトウェア
  - OpenSSH
- クライアントソフトウェア
  - Tera Term
  - PuTTY
  - RLogin
- 認証方式
  - パスワード認証方式
  - 公開鍵認証方式

## 3.2: cron

- N/A

## 3.3: プロセス監視

- `ps`コマンド

## 3.4: ログ管理

### Amazon Linux 2 の場合

- rsyslog
  - `/etc/rsyslog.conf`
    - 以下を設定可能
      - ログの生成元
      - プライオリティ
      - 出力先
  - `/etc/rsyslog.d`ディレクトリ
- 一般的なログの出力先
  - `/var/log/messages`

## 3.5: リンク

### ハードリンク

- 実体ファイル参照
- 元のファイルを削除しても、ハードリンクから実体ファイルに参照可能

### シンボリックリンク

- 元のファイル参照
- 元のファイルを削除すると、実体ファイルを参照できない

## 3.6: マウント

- N/A

## 3.7: パッケージ管理

- N/A

## 3.8: パーミッション

- N/A

## 3.9: コマンド

- N/A

## 3.10: 正規表現

- N/A