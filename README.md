# JapanAbductionWatch.org — 静的サイト

WordPress(EasyWP)版の後継。GitHub Pages + Airtable埋め込みで運用する。

## 構成

| ファイル | 内容 |
|---|---|
| index.html | ミッションステートメント |
| cases.html | 誘拐実行者データベース（Airtable「Approved Cases」ビュー埋め込み） |
| children.html | 被害児童ギャラリー（Airtable「Victim List」Gallery埋め込み） |
| report.html | 被害報告フォーム（Airtable「Report a New Abduction Case」フォーム埋め込み） |
| CNAME | カスタムドメイン設定（japanabductionwatch.org） |

## デプロイ手順（GitHub Pages）

1. GitHubで新規リポジトリ作成（例: `japanabductionwatch/site`、Public）
2. このフォルダの全ファイルをアップロード（Web UIの "uploading an existing file" でドラッグ&ドロップ可）
3. Settings → Pages → Source: `main` ブランチ / root → Save
4. Settings → Pages → Custom domain に `japanabductionwatch.org` を入力 → Enforce HTTPS をON

## NameCheap DNS設定（Advanced DNS）

| Type | Host | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | `<GitHubユーザー名>.github.io.` |

## Airtable埋め込みリンクの差し込み（要: Takuya自身の操作）

共有リンクの発行はアクセス権の変更にあたるため、Airtable側での発行操作は本人が行うこと。

1. **cases.html**: base「Abduction」→ Abduction Cases → 「Approved Cases」ビュー → Share and sync → 共有リンク作成 → 埋め込みコード内URLを `AIRTABLE_CASES_EMBED` コメント箇所のiframeに貼る
2. **children.html**: Victim List → Gallery ビュー → 同様に `AIRTABLE_CHILDREN_EMBED` へ
3. **report.html**: Forms → Report a New Abduction Case → Share form → URLを `AIRTABLE_FORM_EMBED` へ

※ 公開されるのは共有したビューのみ。「Approved Cases」（Consent to Publish?承認済みのみ表示）を共有すれば未承認案件は公開されない。

## 運用フロー（前回と同じ）

被害者がフォームで自己申告 → Abduction Casesに未承認レコードとして入る → 証拠書類・公開同意を確認 → Consent to Publish? を承認 → 公開ビューに自動表示

## 注意

- ドメイン期限: 2026-08-17（NameCheap、要更新確認）
- 係争中の自案件（Kairi Futami）の掲載は弁護士確認後に判断すること
