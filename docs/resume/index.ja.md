# 職務経歴書

## 職務要約

MLOps チームリード（5 名）として、DAU 20 万人（累積 640 万 NUU）のタイトル向け ML 推論基盤を 0→1 で設計・構築。**Spanner クエリ最適化（CPU 83% 削減、特徴量集計 SQL Read 平均レイテンシ 100ms→20ms）、Dataflow ストリーミングパイプライン設計（CloudRun 20台→1台）、運用コスト 30% 削減（$200/day→$140/day）を達成**。Query Insights で複数回テーブルスキャンを特定し CTE+JOIN を排除、Terraform IaC（5000+ lines）による全インフラのコード化を推進。DS/Data との技術的トレードオフ分析（レイテンシ vs コスト vs 精度）を主導し、3 チーム横断で合意形成を実現。

---

## コアスキル・技術スタック

### プログラミング言語

| 言語 | 経験年数 | 主要技術・フレームワーク | 実務経験 |
|-----|---------|----------------------|---------|
| **Python** | 4 年 + 3 年 | Gunicorn, FastAPI, Pydantic, Kubeflow, Airflow, PyTorch, Pandas, Polars, dbt, Apache Beam | ML 推論 API 開発、データパイプライン構築 |
| **Java** | 3 年 | Apache Beam | Dataflow ストリーミングパイプライン |
| **Terraform** | 3 年 | HCL | IaC による GCP インフラ管理、CI/CD パイプライン構築 |
| **SQL** | 2 年 | BigQuery, Spanner, dbt | データ分析、クエリ最適化、Feature Store 設計 |
| **Go** | 1 年 | - | サーバー・バッチジョブ実装 |

**開発環境**: uv, ruff, ty, pytest, sqlfluff, pre-commit

### Google Cloud Platform

| カテゴリ | サービス |
|---------|---------|
| **Compute** | CloudRun, Vertex AI Pipelines, Composer |
| **Data** | BigQuery, Spanner, CloudStorage, Firestore |
| **Streaming** | Pub/Sub, Dataflow |
| **ML** | Vertex AI Workbench, Vertex AI Pipelines |
| **Ops** | CloudLogging, CloudMonitoring, Artifact Registry |

### インフラ・DevOps・MLOps

| 領域 | 技術・ツール |
|-----|-----------|
| **IaC** | Terraform |
| **Container** | Docker |
| **CI/CD** | GitHub Actions |
| **ML Workflow** | Kubeflow, Vertex AI Pipelines |
| **Data Workflow** | dbt (Composer によるオーケストレーション) |
| **専門領域** | リアルタイム・バッチ推論、Feature Store、ML パイプラインオーケストレーション、モデルデプロイ自動化、コスト最適化 |

### 保有資格

| 資格 | リンク |
|-----|-------|
| Google Cloud Certified - Associate Cloud Engineer | [Credly](https://www.credly.com/badges/921248ee-3e36-48ab-a2eb-7984bc97e5ca/public_url) |
| Google Cloud Certified - Professional Cloud Developer | [Credly](https://www.credly.com/badges/3456384c-0eab-474c-a7b6-c29ee5bfdf9c/public_url) |

---

## 職務経歴

### 株式会社ディー・エヌ・エー
**IT本部 AI・データ戦略統括部 データ基盤部 ゲームエンタメ第一グループ**
**MLOps エンジニア**
**2023 年 4 月 - 現在**

#### プロジェクト一覧

| # | プロジェクト名 | 期間 | 役割 | 主要成果 |
|---|-------------|------|------|---------|
| 1 | ニアリアルタイム / バッチ ML 推論基盤<br>DAU 20 万人, 累積 640 万 NUU | 2023/04 - 現在 | MLOps チームリード（5 名）<br>設計・実装・最適化を主導 | Spanner CPU 83% 削減、CloudRun 20台→1台、コスト 30% 削減、技術的トレードオフ分析を主導 |

---

### 1. ML 推論基盤（DAU 20 万人、累積 640 万 NUU）

#### プロジェクト概要

| 項目 | 内容 |
|-----|------|
| **目的** |ユーザー体験向上のためのニアリアルタイム / バッチ ML 推論基盤の設計・構築・運用 |
| **スケール** | 累積 640 万 NUU（New Unique Users）, DAU 20 万人 |
| **期間** | 2023 年 4 月 - 現在（継続的な開発・改善） |
| **役割** | MLOps チームリード（5 名をリード、アーキテクチャ設計・実装・最適化を主導、DS/Data チームと協働） |
| **チーム構成** | MLOps: 5 名、Data: 5 名、DS: 2 名 + バックエンド・クライアント（複数チーム）の計 12+ 名と協働 |

#### 担当役割・責任範囲

| 領域 | 詳細 |
|-----|------|
| **アーキテクチャ設計** | システム全体のアーキテクチャ設計、GCP サービスの技術選定と組み合わせ戦略、スケーラビリティ・可用性・コスト効率を考慮した設計方針の策定 |
| **実装** | 推論 API（FastAPI + Gunicorn + CloudRun、TTL 付きキャッシュ 24h）、ニアリアルタイム特徴量生成パイプライン（Pub/Sub → Dataflow (Apache Beam/Java: ログフィルタ 55% 削減 + Window 集約) → Pub/Sub → CloudRun (Python: 特徴量集計) → Spanner）、ML パイプライン（Vertex AI Pipelines） |
| **インフラ構築・IaC** | Terraform による全インフラのコード化、CI/CD パイプラインの設計・構築、セキュリティ・ネットワーク設計 |
| **運用・最適化** | 監視・アラート体制の構築（CloudLogging, CloudMonitoring）、パフォーマンスチューニング、コスト最適化施策の立案・実行 |
| **チーム横断推進** | DS とのモデル要件定義・パフォーマンス改善協議、Data エンジニアとのデータパイプライン設計調整、バックエンド・クライアントチームとの API 仕様策定・連携 |

##### 主要技術スタック

- **GCP**: CloudRun (推論 API、特徴量集計)、Spanner (特徴量ストア)、Dataflow (ストリーミングパイプライン)、Pub/Sub (イベントハブ)、Vertex AI Pipelines (ML ワークフロー)、BigQuery (データ分析)
- **IaC**: Terraform による全インフラのコード化

#### 主要プロジェクト実績

##### 1. クロスファンクショナル合意形成（リアルタイム vs バッチ推論）

| 項目 | 内容 |
|-----|------|
| **Situation** | DS チームは「全ログをリアルタイム処理」を要望（レイテンシ最小化）、MLOps/Data チームは「実装・運用コストの増大」を懸念。 |
| **Task** | レイテンシ・モデル精度の 2 軸で定量分析し、ビジネス価値を最大化するアーキテクチャを決定 |
| **Action** | • **定量分析**: **p95 レイテンシ 50ms（バッチ） vs 150ms（リアルタイム想定）、SLO 80ms は両方達成可能**<br>• **仮説検証**: **24時間周期バッチ推論でも AUC 0.8 以上維持**を DS と共同で実証<br>• **提案と合意形成**: バッチ推論（Vertex AI Pipelines）への切り替えを提案し、DS/Data/MLOps の 3 チーム合意を獲得<br>• **実装リード**: MLOps チーム 5 名の task 分解・レビュー・ブロッカー解消を主導 |
| **Result** | • **DS/Data/MLOps 3 チーム合意**、バッチ推論（Vertex AI Pipelines）へ方針決定<br>• モデル精度維持（AUC 0.8 以上）、**実装工数大幅削減によりリリース期限達成** |

##### 2. Spanner パフォーマンスチューニング（CPU 83% 削減、レイテンシ 80% 改善）

| 項目 | 内容 |
|-----|------|
| **Situation** | リリース直後、バッチ ML 推論結果の書き込みで Spanner CPU 100% 到達、2-4 Nodes へ自動スケールし、一時的にレイテンシが悪化 |
| **Task** | 1 Node で安定稼働させつつ、レイテンシを向上させる |
| **Action** | • **根本原因分析**: Query Insights で複数回テーブルスキャンを特定（CPU 30% の原因）<br>• **クエリ最適化**: 構造を根本再設計（複数 CTE+JOIN → 単一スキャン+GROUP BY）<br>• **DS/Data チームと協議**: 特徴量取得頻度を最適化 |
| **Result** | • **Spanner CPU 83% 削減**（30%→5%）、1 Node 安定稼働<br>• **特徴量集計 SQL Read レイテンシ p95 で 80% 改善**（100ms→20ms） |

##### 3. ストリーミングパイプライン最適化（CloudRun 20台→1台）

| 項目 | 内容 |
|-----|------|
| **Situation** | ニアリアルタイムに特徴集計をする CloudRun インスタンス **20台が常時稼働**しコスト増大懸念 |
| **Task** | CloudRun インスタンス数を削減しつつ、特徴計算を維持 |
| **Action** | • **上流フィルタリング**: Dataflow（Apache Beam/Java）で不要なログ種別を **55% フィルタリング**<br>• **Window 集約**: Fixed Window（60秒）で時系列集約を実施し、**特徴集計回数を 95% 削減**<br>• **疎結合化**: Pub/Sub による非同期処理でパイプライン安定性向上 |
| **Result** | • **CloudRun インスタンス数 95% 削減（20台→1台）**<br>• 特徴量精度を維持しつつ、運用コスト削減達成 |

##### 4. バッチ ML パイプライン構築（24時間サイクル、ReverseETL）

| 項目 | 内容 |
|-----|------|
| **Situation** | バッチ推論結果を Spanner へ連携する際、BQ からの直接書き込みでは Spanner 負荷増大と BQ コスト増大の懸念 |
| **Task** | Spanner 負荷と BQ コストを削減しつつ、推論結果を迅速に Spanner へ連携 |
| **Action** | • **Vertex AI Pipelines**: 24時間サイクルでバッチ推論を実行し、結果を BQ へ書き込み<br>• **BQ → GCS export**: BigQuery から Cloud Storage へ効率的にエクスポート<br>• **Dataflow による ReverseETL**: Dataflow（Apache Beam）で GCS から読み取り、Spanner へバッチ書き込み<br>• **疎結合化**: BQ と Spanner を直接接続せず、GCS を中間層として安定性向上 |
| **Result** | • **Spanner 負荷削減と BQ コスト削減を両立**<br>• 24時間サイクルで推論結果を安定的に Spanner へ連携<br>• エンドツーエンド ML パイプラインの確立 |

---

**最終更新日**: 2026 年 8 月 6 日
