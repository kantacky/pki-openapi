# OpenAPI 実装タスクリスト

## 高優先度タスク

### 1. OpenAPI 基本構造の設計

- [x] OpenAPI 3.1.0 仕様に準拠した基本構造を作成
- [x] API 基本情報（title, version, description）を設定
- [x] サーバー情報を定義
- [x] 認証方式（OAuth2, API Key 等）を定義

### 2. 証明書管理エンドポイントの実装

- [x] POST /certificates - 証明書の作成・発行
- [x] GET /certificates/{id} - 証明書の取得・参照
- [x] PUT /certificates/{id} - 証明書の更新・再発行
- [x] DELETE /certificates/{id} - 証明書の失効・削除
- [x] GET /certificates - 証明書の検索・一覧表示

### 3. CA 管理エンドポイントの実装

- [x] POST /ca/root - ルート CA 証明書の作成
- [x] GET /ca/root - ルート CA 証明書の取得
- [x] POST /ca/intermediate - 中間 CA 証明書の作成
- [x] GET /ca/intermediate - 中間 CA 証明書の一覧
- [x] GET /ca/hierarchy - CA 階層の構築・管理
- [x] GET /ca/crl - CA 証明書の失効リスト（CRL）管理

### 4. データモデルとスキーマの定義

- [x] Certificate スキーマ定義
- [x] CertificateAuthority スキーマ定義
- [x] CertificateRequest スキーマ定義
- [x] Key スキーマ定義
- [x] Template スキーマ定義
- [x] エラーレスポンススキーマ定義

## 中優先度タスク

### 5. 証明書検証エンドポイントの実装

- [x] POST /certificates/{id}/validate - 証明書の有効性確認
- [x] POST /certificates/validate-chain - 証明書チェーンの検証
- [x] GET /ocsp/{serialNumber} - OCSP レスポンダー
- [x] GET /certificates/{id}/status - 証明書失効状態の確認

### 6. キー管理エンドポイントの実装

- [x] GET/POST /keys - キー一覧取得・生成
- [x] GET/PUT/DELETE /keys/{id} - 個別キー操作
- [x] POST /keys/{id}/backup - キーペアのバックアップ
- [x] POST /keys/{id}/restore - キーペアの復元
- [x] POST /keys/{id}/rotate - キーのローテーション

### 7. セキュリティ・テンプレート・通知機能の実装

- [x] POST /auth/login - API 認証
- [x] GET /audit/logs - 監査ログ
- [x] GET/POST /templates - 証明書テンプレートの管理

### 8. インポート・エクスポート機能の実装

- [x] POST /certificates/import - 証明書インポート（PEM/PKCS#12）
- [x] POST /certificates/export - 証明書エクスポート（複数形式対応）

## 低優先度タスク

### 9. レポート・統計機能の実装

- [x] GET /reports/issuance - 証明書発行統計
- [x] GET /reports/usage - 使用状況レポート

## 技術的考慮事項

### セキュリティ

- [ ] TLS/HTTPS の設定
- [ ] 認証・認可の実装
- [ ] 入力値検証
- [ ] レート制限

### エラーハンドリング

- [ ] 統一されたエラーレスポンス形式
- [ ] 適切な HTTP ステータスコード
- [ ] エラーメッセージの国際化対応

### パフォーマンス

- [ ] ページネーション実装
- [ ] フィルタリング機能
- [ ] ソート機能
- [ ] キャッシュ戦略

### 運用

- [ ] ヘルスチェックエンドポイント
- [ ] メトリクス収集
- [ ] ログ記録
- [ ] API バージョニング
