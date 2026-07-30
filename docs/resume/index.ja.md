# 職務経歴書

## 職務要約

MLOps エンジニアとして、ゲームタイトル（累積 640 万 NUU・DAU 20 万人）における ML 推論基盤を 0→1 で設計・構築。

**技術的成果**:

1. **Spanner CPU スパイク解決**: クエリ構造再設計で **CPU 83% 削減** (30% → 5%)、1 Node で安定稼働
2. **特徴量生成パイプライン最適化**: Dataflow ログフィルタ 55% 削減 + Window 集約により **Cloud Run CPU 97% 削減**
3. **ScoreAPI 最適化**: TTL 付きインメモリキャッシュ（24h）で一時的なレイテンシ増加を改善
4. **コスト最適化**: 段階的スケールイン + 詳細最適化により **月額コスト $4.2k** で運用（$2.5k/day → $140/day）

**技術スタック**: GCP（Spanner, Dataflow, Vertex AI Pipelines, Cloud Run）、Python/Java/Terraform

**資格・実績**: GCP Professional 認定、国際会議論文採択 (IWAIT 2023)、OSS 貢献 (Spanner AutoScaler)

---

## コアスキル・技術スタック

### プログラミング言語
- **Python（主要）**: FastAPI, PyTorch, Pandas, Polars, dbt, Apache Beam / 開発: uv, ruff, ty, pytest, pre-commit
- **Java**: Apache Beam（Dataflow パイプライン）
- **Terraform**: IaC による GCP インフラ管理
- **Go**: CLI ツール実装

### Google Cloud Platform
- **Compute**: Cloud Run, Vertex AI Pipelines
- **Data**: BigQuery, Cloud Spanner, Cloud Storage
- **Streaming**: Pub/Sub, Dataflow
- **ML**: Vertex AI Workbench, Vertex AI Pipelines
- **Ops**: Cloud Logging, Cloud Monitoring, Artifact Registry

### インフラ・DevOps・MLOps
- **IaC**: Terraform / **Container**: Docker / **CI/CD**: GitHub Actions
- **ML Workflow**: Kubeflow, Vertex AI Pipelines
- **専門領域**: リアルタイム・バッチ推論、Feature Store、ML パイプラインオーケストレーション、モデルデプロイ自動化、コスト最適化

### 保有資格
- [Google Cloud Certified - Associate Cloud Engineer](https://www.credly.com/badges/921248ee-3e36-48ab-a2eb-7984bc97e5ca/public_url)
- [Google Cloud Certified - Professional Cloud Developer](https://www.credly.com/badges/3456384c-0eab-474c-a7b6-c29ee5bfdf9c/public_url)

---

## 職務経歴

### 株式会社ディー・エヌ・エー
**IT本部 AI・データ戦略統括部 データ基盤部 ゲームエンタメ第一グループ**
**MLOps エンジニア**
**2023 年 4 月 - 現在**

#### プロジェクト一覧

| # | プロジェクト名 | 期間 | 役割 | 主要成果 |
|---|-------------|------|------|---------|
| 1 | リアルタイム ML 推論基盤（ゲーム）<br>累積 640 万 NUU, DAU 20 万人 | 2023/04 - 現在 | MLOps エンジニア | Spanner CPU スパイク解決、ノード数 75% 削減、月額コスト 80%+ 削減 |

---

### 1. リアルタイム ML 推論基盤（累積 640 万 NUU, DAU 20 万人）

#### プロジェクト背景

**ビジネス課題**:

- ゲーム業界における競争激化により、ユーザー体験のパーソナライゼーションが重要な差別化要因に
- 既存のバッチ処理ベースのレコメンデーションでは、ユーザーの行動変化への即応性が不足
- リアルタイム ML 推論によるゲーム内コンテンツ配信・パーソナライゼーションのニーズ

**技術的課題**:

- リアルタイム性（低レイテンシ）とインフラコスト効率のトレードオフ
- DAU 20 万人、累積 640 万 NUU のトラフィックを安定的に処理できるスケーラビリティ
- 市販の MLOps プラットフォームでは、ゲーム特有の要件（バーストトラフィック、コスト制約）を満たせない

**ソリューション**:

- GCP のマネージドサービスを組み合わせた独自の MLOps 基盤を設計・構築
- データドリブンなコスト最適化により、ビジネス価値とコスト効率を両立

#### プロジェクト概要

| 項目 | 内容 |
|-----|------|
| **目的** | ゲームタイトルにおけるユーザー体験向上のための ML モデルによるリアルタイム推論基盤の設計・構築・運用 |
| **スケール** | 累積 640 万 NUU（New Unique Users）, DAU 20 万人 |
| **期間** | 2023 年 4 月 - 現在（継続的な開発・改善） |
| **役割** | MLOps エンジニア（アーキテクチャ設計・実装・最適化を主導、DS/Dataチームと協働） |
| **チーム構成** | MLOps: 5 名、Data: 5 名、DS: 2 名 + バックエンド・クライアント（複数チーム）の計 12+ 名と協働 |

#### 担当役割・責任範囲

| 領域 | 詳細 |
|-----|------|
| **アーキテクチャ設計** | システム全体のアーキテクチャ設計、GCP サービスの技術選定と組み合わせ戦略、スケーラビリティ・可用性・コスト効率を考慮した設計方針の策定 |
| **実装** | リアルタイム推論 API（FastAPI + Gunicorn + Cloud Run）、特徴量生成パイプライン（Pub/Sub → Dataflow (Apache Beam/Java: ログフィルタ 55% 削減 + Window 集約) → Pub/Sub → Cloud Run (Python: 特徴量集計) → Spanner）、スコア算出 API（ScoreAPI: Cloud Run）、ML パイプライン（Vertex AI Pipelines） |
| **インフラ構築・IaC** | Terraform による全インフラのコード化、CI/CD パイプラインの設計・構築、セキュリティ・ネットワーク設計 |
| **運用・最適化** | 監視・アラート体制の構築（Cloud Logging, Cloud Monitoring）、パフォーマンスチューニング、コスト最適化施策の立案・実行 |
| **チーム横断推進** | DS とのモデル要件定義・パフォーマンス改善協議、Data エンジニアとのデータパイプライン設計調整、バックエンド・クライアントチームとの API 仕様策定・連携 |

##### 技術スタックと選定理由

| 技術 | 用途 | 選定理由 |
|-----|------|---------|
| **Cloud Run** | ①推論 API (FastAPI)、②特徴量集計 (Pub/Sub トリガー、CPU 97% 削減達成)、③ScoreAPI (スコア算出) | オートスケーリング、コンテナベースでのデプロイ容易性、従量課金モデルによるコスト効率 |
| **Cloud Spanner** | リアルタイム特徴量ストア | グローバル一貫性、水平スケーラビリティ、低レイテンシ（10ms 未満）な読み取り性能、99.999% の SLA |
| **Dataflow (Apache Beam)** | 特徴量生成パイプライン（ログフィルタ 55% 削減 + Window 集約で下流負荷削減） | ストリーミング・バッチ処理の統一的な記述、自動スケーリング、Java による高速処理 |
| **Pub/Sub** | イベント駆動アーキテクチャ（行動ログ取り込み + パイプライン間連携） | 非同期メッセージング、少なくとも一回配信保証、スケーラブルなイベントハブ、パイプライン疎結合化 |
| **Vertex AI Pipelines** | ML ワークフローオーケストレーション | Kubeflow ベースの標準化された ML パイプライン、再現性の確保、バージョン管理 |
| **BigQuery** | データウェアハウス・分析基盤 | テラバイトスケールのクエリ性能、ML モデル学習用データの集約・分析 |
| **Cloud Storage** | モデル成果物・ログ保存 | 高耐久性、低コスト、GCP サービス間の統合性 |
| **Terraform** | IaC | インフラの再現性・変更管理、コードレビューによる品質担保、複数環境の一元管理 |

**アーキテクチャパターン**:

- **イベント駆動アーキテクチャ**: Pub/Sub を中核としたリアルタイムイベント処理
- **Lambda アーキテクチャの変形**: リアルタイム推論（Cloud Run）とバッチ推論（Vertex AI Pipelines）のハイブリッド
- **Feature Store パターン**: Spanner を特徴量ストアとして、オンライン特徴量とオフライン特徴量の統一管理

##### 技術的深掘り: Spanner 最適化の詳細

#### 1. Spanner CPU スパイク問題の解決

**問題**: ML 推論結果書き戻し時に CPU 100% 超過、2-4 Nodes に自動スケール

**解決**: クエリ構造の根本的再設計（複数回スキャン → 1回スキャン、JOIN 排除）

**成果**: **CPU 83% 削減** (30% → 5%)、1 Node で安定稼働

#### 2. 特徴量生成パイプラインの最適化

**問題**: Cloud Run の CPU 負荷が高い

**解決**: Dataflow ログフィルタ（55% 削減）+ Window 集約 + Pub/Sub 疎結合

**成果**: **Cloud Run CPU 97% 削減**

#### 3. ScoreAPI のパフォーマンス最適化

**問題**: トラフィック集中時にレイテンシ増加

**解決**: TTL 付きインメモリキャッシュ（24h、LRU）導入

**成果**: レイテンシ改善、Spanner 負荷削減

#### 4. コスト最適化

**段階的な削減**: $2,500/day（リリース日）→ $200/day（段階的スケールイン、92% 削減）→ $140/day（詳細最適化、94% 削減）

**施策**: Spanner クエリ最適化、Dataflow ログフィルタ、Cloud Run 課金モデル変更

**成果**: 主に 30% のコスト削減

---

### 学びと今後への展開

| 観点 | 学び |
|-----|------|
| **スケールとコストのトレードオフ設計** | 初期設計時から段階的スケールイン戦略を組み込む重要性。トラフィック予測の不確実性に対するリスクヘッジと、過剰プロビジョニング回避のバランス |
| **データサイエンティストとのコミュニケーション** | 技術的制約をビジネス要件に翻訳し、最適解を共に探る姿勢。「リアルタイム推論が必要か?」という本質的な問いを投げかける重要性 |
| **クラウドネイティブ技術の深い理解** | GCP サービスの特性を深く理解し、適材適所で組み合わせる設計力。Spanner, Dataflow, Pub/Sub などのマネージドサービスの恩恵を最大化 |
| **MLOps のエンドツーエンド視点** | モデル開発から本番運用、コスト最適化まで一気通貫で考える視点の重要性。CI/CD、監視、アラート、コスト管理すべてを含めた総合的な基盤設計 |

---

## 志向性・今後のキャリア

### 大切にしている価値観

#### 1. データドリブンな意思決定
- 体感ではなく、測定可能な指標での改善（CPU 30% → 5%、コスト $2.5k → $140/day）
- 数値に基づく技術選定・最適化
- A/B テストや実験による仮説検証の文化

#### 2. ユーザーファースト
- コスト削減のためにユーザー体験を犠牲にしない
- DS との協議でリアルタイム性の必要性を精査
- 技術的制約とユーザー価値のバランスを常に意識

#### 3. 継続的な学習と発信
- OSS 貢献（Spanner AutoScaler）、技術記事執筆（Zenn/Qiita）
- 新技術の早期採用と実践（uv, ty, Ruff など Astral 社エコシステム）
- コミュニティへの知見還元

### 今後挑戦したいこと

#### 1. グローバル分散システムへの深化

**現在の課題認識**:

- Spanner を 3 年間運用し、**ホットスポット問題**や**クエリ最適化**を経験
- しかし、あくまで **"利用者"** としての視点
- **"設計者"** としての視点（内部実装の理解）が不足していると痛感

**具体的な関心**:

- **分散合意アルゴリズム**: Paxos/Raft の理論を深く学び、実装経験を積みたい
    - 現在: Spanner の挙動を外から観察
    - 次: 分散データベースを自分で設計・実装し、トレードオフを体感
- **物理時刻同期**: TrueTime のような機構がなぜ必要か、どう実装するか
    - GPS/原子時計を使った時刻同期の実践
    - 時刻のずれが分散システムに与える影響の定量的理解
- **グローバルトランザクション**: マルチリージョンでの一貫性とレイテンシのトレードオフ
    - 現在: 東京リージョンのみ
    - 次: グローバルユーザーに対する最適なデータ配置戦略

**Why this matters to me**:
Spanner を使いこなすだけでなく、**"なぜそう設計されているか"** を理解することで、次世代の分散システムを設計できるエンジニアになりたい

#### 2. ML システムのスケーラビリティ - 次の桁へ

**現在の限界**:

- DAU 20 万人で月額 $4.2k のコストを達成
- しかし、**10 倍のスケール（DAU 200 万人）になったら？**
    - 単純計算: $42k/月（現実的には非線形に増大）
    - Spanner の read/write スループット限界
    - ML モデルサイズとレイテンシのトレードオフ

**挑戦したい技術領域**:

- **モデル圧縮**: 量子化・蒸留・pruning による推論速度向上
    - 現在: フルサイズモデルをそのまま推論
    - 次: 精度を維持しつつ、10 倍高速な推論を実現
- **オンライン学習**: バッチ学習の限界を超える
    - 現在: 日次バッチで学習 → デプロイ
    - 次: ユーザーの行動を即座に反映する継続学習
- **Observability**: 数百万 DAU でのモデル挙動の可視化
    - 現在: 基本的なメトリクス（レイテンシ、エラー率）
    - 次: Feature drift、Prediction distribution shift の自動検知

**本質的な問い**:
DAU 20 万人 → 200 万人 → 2000 万人と成長するとき、**どこがボトルネックになり、どう解決するか？** を実践で学びたい

---

## 学歴・研究実績

### 中京大学 工学部 情報工学科
**2019 年 4 月 - 2023 年 3 月**

#### 研究活動
**研究テーマ**: 医療画像 AI（腹部超音波画像からの肝腫瘍検出・分類）

**研究成果**:

- **国際会議論文採択**: [Liver tumor detection and classification from abdominal ultrasound images with centernet using contrastive learning](https://www.spiedigitallibrary.org/conference-proceedings-of-spie/12592/125920E/Liver-tumor-detection-and-classification-from-abdominal-ultrasound-images-with/10.1117/12.2662969.short)
    - 著者: 原英吾, 道満恵介, 目加田慶人, 西田直生志, 工藤 正俊
    - 会議: International Workshop on Advanced Image Technology (IWAIT) 2023, Jeju, Korea
    - 発表年月: 2023 年 1 月

**技術要素**:

- 深層学習（CenterNet アーキテクチャ）
- Contrastive Learning（対照学習）による特徴表現学習
- 医療画像処理（超音波画像の前処理・データ拡張）
- PyTorch, OpenCV

#### 登壇活動
- [ML Career Vision #1 「新卒MLエンジニアのキャリアヴィジョン」](https://elith.connpass.com/event/272218/)（2023 年 2 月）
    - 新卒 ML エンジニアとしてのキャリア形成について登壇

### 愛知県立刈谷高等学校
**2015 年 4 月 - 2018 年 3 月**

---

## インターンシップ経験

### ギリア株式会社
**AI エンジニア（有給インターン）**
**2021 年 9 月 - 2022 年 9 月（1 年間）**

学生時代から実務経験を積み、機械学習モデルの開発に従事。

**主な業務:**

- 機械学習モデルの設計・実装・評価
- モデルの本番環境へのデプロイと運用
- データパイプラインの構築

**技術スタック:**

- Python
    - PyTorch
    - Scikit-learn
    - Pandas
    - OpenCV

**学び:**

- 実務レベルの ML モデル開発プロセスの理解
- チーム開発・コードレビュー文化の体験

---

## OSS 活動・技術発信

### OSS 貢献

#### Spanner AutoScaler - Cloud Run Functions 2nd Generation 対応
**PR**: [https://github.com/cloudspannerecosystem/autoscaler/pull/196](https://github.com/cloudspannerecosystem/autoscaler/pull/196)

**背景・課題**:

- Google Cloud の公式 Spanner AutoScaler は Cloud Run Functions 1st Generation のみサポート
- 2nd Generation は新アーキテクチャ（コンカレンシーモデル、起動時間など）で優位性があるが、未対応

**実装内容**:

- Cloud Run Functions 2nd Generation の新アーキテクチャに対応
- イベントハンドラーのインターフェース変更に対応
- 後方互換性を維持しながら、両世代をサポート

**技術的意義**:

- GCP の最新サービスへの追従
- パフォーマンス・スケーラビリティの向上
- コミュニティへの貢献（Google Cloud 公式エコシステムプロジェクト）

### 技術記事執筆

**Zenn**（DeNA 公式アカウント含む）:

- [Python 開発環境を uv で統一管理する](https://zenn.dev/dena/articles/python_env_with_uv)
    - Python の次世代パッケージマネージャー uv の実践的な活用方法
    - DeNA 社内での標準化事例
- [Rye + DevContainer で Python 開発環境を標準化](https://zenn.dev/dena/articles/rye_python_in_devcontainer)
    - チーム開発における Python 環境の標準化手法
    - 再現可能な開発環境構築のベストプラクティス
- [Terraform + DevContainer で IaC 開発環境を標準化](https://zenn.dev/dena/articles/terraform_with_devcontainer)
    - Terraform 開発のベストプラクティスと環境構築

**Qiita**:

- [ナンプレを AI に解かせてみる](https://qiita.com/a5chin/items/6d35283a54a1022f9b24)
    - 制約充足問題としての数独解法の AI 実装

### 公開プロジェクト

#### MLOps・インフラ系
- **[ml-pipelines](https://github.com/a5chin/ml-pipelines)**: Kubeflow Pipelines (KFP) の production-ready テンプレート
    - **技術**: Python 3.10+, Kubeflow, uv, ty, Ruff, SQLFluff, Pydantic, Docker, Pytest, GitHub Actions
    - **特徴**: タスクベースのモジュラー設計、マルチ環境対応（dev/prod）、型安全な設定管理、CI/CD 完備
    - **価値**: 実務で培った MLOps ベストプラクティスをテンプレート化し、コミュニティに還元
- **[terraform-template](https://github.com/a5chin/terraform-template)**: Terraform 開発環境の標準化テンプレート
    - IaC 開発のベストプラクティスと DevContainer による環境統一

#### 開発環境標準化
- **[python-uv](https://github.com/a5chin/python-uv)**: Python 開発環境の標準化テンプレート
    - 次世代パッケージマネージャー uv を活用した高速・再現可能な環境構築

#### 機械学習応用
- **[NumberPlaceSolver](https://github.com/a5chin/NumberPlaceSolver)**: AI によるナンプレ（数独）ソルバー
    - 制約充足問題への機械学習アプローチの実装例

### 技術コミュニティ活動
- GitHub での継続的な OSS 活動
- Zenn, Qiita での知見共有（計 4 記事以上）
- 技術イベント登壇（ML Career Vision）

---

## リンク
- [X (Twitter)](https://x.com/a5chin)
- [LinkedIn](https://linkedin.com/in/a5chin)
- [GitHub](https://github.com/a5chin)
- [Zenn](https://zenn.dev/a5chin)
- [Qiita](https://qiita.com/a5chin)

---

**最終更新日**: 2026 年 7 月 30 日
