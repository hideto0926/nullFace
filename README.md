# web — 紹介ページとプライバシーポリシー

アプリ名は **NullFace**。App Store Connect の「マーケティング URL」と「プライバシーポリシー URL」に使えます。

静的な HTML だけで動きます（ビルド不要・外部読み込みなし）。そのまま GitHub Pages などに置けます。

| ファイル | 用途 |
| --- | --- |
| `index.html` | アプリ紹介ページ 日本語（App Store の「マーケティング URL」向け） |
| `privacy.html` | プライバシーポリシー 日本語（App Store Connect の「プライバシーポリシー URL」向け） |
| `en/index.html` | 紹介ページ 英語 |
| `en/privacy.html` | プライバシーポリシー 英語 |
| `assets/style.css` | 2 ページ共通のスタイル（ライト / ダーク対応） |
| `assets/icon.png` | アプリアイコン 256px（favicon・ヘッダー用）。元は `../sozai/IMG_3302.heic` |
| `assets/icon-large.png` | 同 640px。先頭で大きく見せる用 |
| `assets/shots/` | スクリーンショットの置き場所（下記） |

## スクリーンショット

`assets/shots/` に配置済みです（長辺 1170px・すべて**明るめテーマ**で統一）。
ライブラリ・見せる範囲・設定は実機（`../sozai/`）、1 枚表示・非表示の一覧・使い方はシミュレータです。
差し替えるときは同じファイル名で上書きしてください。
置いていないファイルは枠にプレースホルダーが出るだけで、レイアウトは崩れません。

| ファイル名 | 画面 |
| --- | --- |
| `01-library.png` | ライブラリ（一覧・実機）|
| `02-detail.png` | 1 枚表示 |
| `03-scope.png` | 見せる範囲の選択 |
| `04-settings.png` | 設定 |
| `05-hidden.png` | 非表示になっている写真 |
| `06-onboarding.png` | 使い方（オンボーディング） |

枠の縦横比は 9:19.5（iPhone の実機スクリーンショットそのまま）です。別の比率にする場合は
`assets/style.css` の `.shot .frame { aspect-ratio }` を変えてください。

## 確認

```sh
cd web
python3 -m http.server 8000   # → http://localhost:8000/
```

## 日本語と英語

`en/` の中に英語版があります。画像と CSS は `../assets/` を共有しているので、増えるのは HTML 2 枚だけです。
ヘッダーとフッターに相互のリンクを置き、`<link rel="alternate" hreflang>` も入れてあります。

App Store Connect では、ロケールごとに URL を設定できます。

| ロケール | マーケティング URL | プライバシーポリシー URL |
| --- | --- | --- |
| 日本語 | `<ドメイン>/` | `<ドメイン>/privacy.html` |
| English | `<ドメイン>/en/` | `<ドメイン>/en/privacy.html` |

文面を直すときは、**日本語版と英語版の両方**を直してください（対訳なので構造は同じです）。
