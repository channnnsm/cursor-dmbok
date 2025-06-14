# データ定義書テンプレート

## データ項目定義フォーマット

各データ項目には以下の情報を含めてください：

---

## [データ項目名]

### ビジネス定義
[このデータ項目が表すビジネス上の意味や概念]

### 技術仕様
- **データ型**: [VARCHAR, INTEGER, DATE など]
- **長さ/精度**: [最大長さや精度]
- **必須項目**: [Yes/No]
- **主キー**: [Yes/No]
- **外部キー**: [参照先テーブル.カラム名]
- **デフォルト値**: [デフォルト値がある場合]
- **許容値/値域**: [取りうる値の範囲や条件]

### データ品質要件
- **検証ルール**: [データの妥当性を確認するための検証ルール]
- **品質基準**: [このデータに期待される品質基準]
- **データクレンジングルール**: [必要に応じたクレンジングのルール]

### 管理情報
- **データオーナー**: [このデータの責任者]
- **データスチュワード**: [日常的な管理責任者]
- **機密性レベル**: [公開/社内限定/機密/極秘 など]
- **保持期間**: [このデータの保存期間]

### データリネージ
- **データ発生源**: [このデータがどこから発生するか]
- **変換プロセス**: [元データからどのような変換が行われるか]
- **下流システム**: [このデータを利用する後続システム]

### 使用状況
- **利用ビジネスプロセス**: [このデータを利用するビジネスプロセス]
- **利用報告書/画面**: [このデータが表示される画面や報告書]
- **利用頻度**: [データの参照/更新の頻度]

---

## データ項目の例

---

## 顧客ID

### ビジネス定義
顧客を一意に識別するための識別子。全社的に統一されたIDで、すべてのシステムで共通利用される。

### 技術仕様
- **データ型**: VARCHAR
- **長さ/精度**: 10文字
- **必須項目**: Yes
- **主キー**: Yes
- **外部キー**: なし
- **デフォルト値**: なし
- **許容値/値域**: 'C'で始まる10桁の英数字

### データ品質要件
- **検証ルール**: 
  - 先頭は'C'であること
  - 2-10桁は数字であること
  - 重複がないこと
- **品質基準**: 完全性100%、正確性100%
- **データクレンジングルール**: なし（システム生成値のため）

### 管理情報
- **データオーナー**: カスタマーサクセス部長
- **データスチュワード**: CRMシステム管理者
- **機密性レベル**: 社内限定
- **保持期間**: 取引終了後10年

### データリネージ
- **データ発生源**: 顧客登録システム
- **変換プロセス**: 自動採番
- **下流システム**: CRM、販売管理、請求システム、マーケティングプラットフォーム

### 使用状況
- **利用ビジネスプロセス**: 顧客管理、受注処理、請求処理、マーケティングキャンペーン
- **利用報告書/画面**: 顧客詳細画面、顧客一覧レポート、売上分析レポート
- **利用頻度**: 非常に高い（1日平均1000回以上の参照）

--- 