# CLAUDE.md - プロジェクト設定ガイド

このファイルは、Claude Codeがプロジェクトを理解し、効果的に作業するためのカスタム設定ファイルです。Claude Codeは起動時に自動的にこのファイルを読み込みます。

## プロジェクト概要

### プロジェクト名
[プロジェクト名を記入]

### 概要
[プロジェクトの目的と主要機能を記述]

### 技術スタック
- **言語**: [使用言語]
- **フレームワーク**: [使用フレームワーク]
- **データベース**: [使用DB]
- **CI/CD**: [使用ツール]
- **その他**: [重要なライブラリやツール]

## GitHub連携設定

### GitHub CLI設定
```bash
# GitHub CLIがインストールされていることを確認
gh auth status

# 必要に応じて認証
gh auth login
```

### リポジトリ情報
- **リポジトリURL**: [GitHubリポジトリURL]
- **メインブランチ**: `main` / `master`
- **開発ブランチ**: `develop` / `dev`

### GitHub Actions
- **ワークフロー設定**: `.github/workflows/`
- **重要なワークフロー**: [CI/CD、テスト、デプロイなど]

## 開発環境セットアップ

### 必須コマンド
```bash
# 依存関係のインストール
[インストールコマンド例: npm install, pip install -r requirements.txt]

# 開発サーバーの起動
[起動コマンド例: npm run dev, python manage.py runserver]

# テストの実行
[テストコマンド例: npm test, pytest]

# ビルド
[ビルドコマンド例: npm run build, make build]

# フォーマット
[フォーマットコマンド例: npm run format, black .]

# リンティング
[リンティングコマンド例: npm run lint, flake8]
```

### 環境変数
```bash
# 必要な環境変数
[環境変数の例]
```

## コーディング規約

### ファイル構造
```
project/
├── src/                # ソースコード
├── tests/              # テストファイル
├── docs/               # ドキュメント
├── .github/            # GitHub Actions
├── .claude/            # Claude Code設定
│   └── commands/       # カスタムコマンド
└── README.md
```

### 命名規則
- **ファイル**: [命名規則]
- **変数**: [命名規則]
- **関数**: [命名規則]
- **クラス**: [命名規則]

### コードスタイル
- **インデント**: [スペース/タブ数]
- **行の長さ**: [最大文字数]
- **その他**: [プロジェクト固有のルール]

## Git ワークフロー

### ブランチ戦略
1. `main` - 本番環境用の安定版
2. `develop` - 開発統合ブランチ
3. `feature/*` - 機能開発用ブランチ
4. `hotfix/*` - 緊急修正用ブランチ

### コミットメッセージ
```
type(scope): description

例:
feat(auth): add user authentication
fix(api): resolve null pointer exception
docs(readme): update installation guide
```

### プルリクエスト
- **テンプレート**: `.github/pull_request_template.md`
- **必須チェック**: テスト通過、コードレビュー承認
- **自動化**: GitHub Actionsによる検証

## テスト戦略

### テストタイプ
- **ユニットテスト**: [テストフレームワーク]
- **インテグレーションテスト**: [設定]
- **E2Eテスト**: [ツール]

### テスト実行
```bash
# 全テスト実行
[テストコマンド]

# 特定テスト実行
[特定テストコマンド]

# カバレッジ確認
[カバレッジコマンド]
```

## MCP（Model Context Protocol）設定

### 利用可能なMCPサーバー
- **GitHub MCP**: GitHub API操作
- **File System MCP**: ファイル操作
- **Shell MCP**: シェル実行
- **[カスタムMCP]**: [説明]

### MCP設定ファイル
`.mcp.json`でチーム共有のMCPサーバーを定義：
```json
{
  "servers": {
    "github": {
      "command": "github-mcp-server",
      "args": ["--token", "$GITHUB_TOKEN"]
    }
  }
}
```

## カスタムコマンド

### プロジェクト固有コマンド
`.claude/commands/`フォルダーにMarkdownファイルとして保存

例: `.claude/commands/deploy.md`
```markdown
# デプロイコマンド
以下の手順でデプロイを実行:
1. テストの実行
2. ビルドの作成
3. 本番環境へのデプロイ
4. ヘルスチェック
```

使用方法: `/project:deploy`

### 個人用コマンド
`~/.claude/commands/`フォルダーに全プロジェクト共通コマンドを保存

## セキュリティとベストプラクティス

### セキュリティ設定
- **機密情報**: `.env`ファイルで管理、Git除外
- **APIキー**: 環境変数で設定
- **権限管理**: 最小権限の原則

### CI/CD統合
```yaml
# .github/workflows/claude-code.yml
name: Claude Code Integration
on:
  pull_request:
    types: [opened, synchronize]
jobs:
  claude-review:
    runs-on: ubuntu-latest
    steps:
      - uses: anthropics/claude-code-action@beta
        with:
          trigger_phrase: "@claude"
```

## トラブルシューティング

### 一般的な問題
1. **依存関係エラー**: [解決方法]
2. **ビルドエラー**: [解決方法]
3. **テストエラー**: [解決方法]

### デバッグコマンド
```bash
# ログ確認
[ログコマンド]

# 状態確認
[状態確認コマンド]

# クリーンアップ
[クリーンアップコマンド]
```

## リソースとドキュメント

### 重要なドキュメント
- **API仕様**: [URL]
- **アーキテクチャ**: [URL]
- **デプロイガイド**: [URL]

### 外部リソース
- **公式ドキュメント**: [URL]
- **コミュニティ**: [URL]
- **問題報告**: [GitHub Issues URL]

## チーム連携

### 連絡先
- **プロジェクトリーダー**: [名前/連絡先]
- **技術責任者**: [名前/連絡先]
- **DevOps**: [名前/連絡先]

### 定期ミーティング
- **開発ミーティング**: [日時]
- **コードレビュー**: [日時]
- **リリース計画**: [日時]

---

## Claude Code使用時の注意事項

### 推奨ワークフロー
1. **計画フェーズ**: 要件を明確化し、タスクを分解
2. **実装フェーズ**: 段階的な実装とテスト
3. **レビューフェーズ**: コード品質とセキュリティの確認
4. **統合フェーズ**: GitHubでのプルリクエストとマージ

### パフォーマンス最適化
- 大きなタスクはMarkdownチェックリストで管理
- 複数のClaude Codeインスタンスを並列で使用可能
- サブエージェントによる専門化されたタスク実行

### セキュリティ注意事項
- `--dangerously-skip-permissions`フラグは慎重に使用
- サンドボックス環境での実行を推奨
- 機密情報へのアクセス権限を制限

このCLAUDE.mdファイルをプロジェクトのルートディレクトリに配置し、プロジェクト固有の情報で更新してください。Claude Codeは起動時にこのファイルを自動的に読み込み、コンテキストとして使用します。
