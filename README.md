# board and cut house — Web公開用ファイル

App Store提出に必要なWebページ一式です。

## 含まれるファイル

- `index.html` — トップページ（アプリ紹介＋各ページへのリンク）
- `support.html` — サポートページ（FAQ、お問い合わせ）
- `privacy.html` — プライバシーポリシー
- `terms.html` — 利用規約
- `commercial-law.html` — 特定商取引法に基づく表記
- `style.css` — 共通スタイル

## デプロイ方法

### オプション1：GitHub Pages（推奨、無料）

1. GitHubにログイン
2. 新しいリポジトリを作成（例: `board-and-cut-house`）
   - Public に設定
3. このフォルダ内の全ファイルをアップロード
4. リポジトリの Settings → Pages
5. Source: `main` branch / `(root)`
6. Save
7. 数分後、URL が発行される（例: `https://[ユーザー名].github.io/board-and-cut-house/`）

### オプション2：Netlify（無料、独自ドメイン可）

1. https://www.netlify.com/ にサインアップ
2. 「Add new site」→「Deploy manually」
3. このフォルダをドラッグ&ドロップ
4. 自動でURL発行（例: `https://random-name.netlify.app/`）
5. 設定で独自ドメインも追加可能

### オプション3：Vercel（無料）

1. https://vercel.com/ にサインアップ
2. 「Add New Project」→「Import」
3. GitHubリポジトリと連携 or ドラッグ&ドロップ
4. デプロイ完了

### オプション4：自前のサーバー

任意のWebサーバーにFTP等でアップロード。

## 公開後にすべきこと

1. **アプリ内のURLを更新**
   - `LegalURLs.swift` の各URLを実際の公開URLに差し替え
   ```swift
   static let termsOfService = "https://your-domain.com/board-and-cut-house/terms.html"
   static let privacyPolicy = "https://your-domain.com/board-and-cut-house/privacy.html"
   static let commercialLaw = "https://your-domain.com/board-and-cut-house/commercial-law.html"
   ```

2. **App Store Connectに登録**
   - Privacy Policy URL: `https://your-domain.com/board-and-cut-house/privacy.html`
   - Support URL: `https://your-domain.com/board-and-cut-house/support.html`
   - Marketing URL（任意）: `https://your-domain.com/board-and-cut-house/`

3. **index.html の App Store リンクを更新**
   - リリース後にApp StoreのURLを取得して、`index.html` の `href="#"` を実際のURLに差し替え

## プレースホルダーの埋め方

全ファイルに以下のプレースホルダーが含まれています。一括置換してください：

| プレースホルダー | 例 |
|---|---|
| `[氏名]` | 山田 太郎 |
| `[YYYY年MM月DD日]` | 2026年4月15日 |
| `[メールアドレス]` | support@example.com |

VSCode等で「フォルダ内検索＆置換」を使うと一括変更できます。

## 注意事項

- **個人情報の公開範囲**
  - 特商法表記では「請求があれば遅滞なく開示」を採用しているため、住所と電話番号は非公開のままで問題ありません
  - メールアドレスは必須（公開前提）
  - 専用のアプリ用メールアドレスを作成することを推奨

- **デザインのカスタマイズ**
  - 全ページとも `style.css` で共通スタイルを管理しています
  - 色やフォントを変更したい場合は CSS の `:root` 変数を編集してください
  - レスポンシブ対応済み（モバイル表示OK）

- **アクセシビリティ**
  - 黒背景・白文字の高コントラストデザイン
  - 文字サイズはレスポンシブで調整される
  - スクリーンリーダー対応の基本的なHTML構造

## ファイル構成

```
board-and-cut-house/
├── index.html          # トップページ
├── support.html        # サポート・FAQ
├── privacy.html        # プライバシーポリシー
├── terms.html          # 利用規約
├── commercial-law.html # 特商法表記
├── style.css           # 共通スタイル
└── README.md           # このファイル
```

## ライセンス

これらのWebページは board and cut house アプリの公式ページとして使用するためのものです。
