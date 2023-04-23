# AWS エンジニア入門講座 - 学習ロードマップで体系的に学ぶ

{docsify-updated}

###### tags: `.AWS`, `.Introduction`, `.Book`, `.Tech`

---

###### サポートページ: https://gihyo.jp/book/2022/978-4-297-12537-0/support

###### クラウドエンジニアロードマップ特設コンテンツ: https://kws-cloud-tech.com/courses/roadmap

---

## 感想

- 入門としては良いがその域を出ない
- 誤字脱字が目立つ
- AWS 以外の用語の説明もあるため、それらを知っているなら学びは減る

---

## Chapter.01: AWS の基礎知識

### 1.1: AWS とは

- IaaS
  - EC2
- PaaS
  - RDS
  - Lambda
- SaaS
  - S3
  - CloudWatch

### 1.2: AWS Well-Architected フレームワーク

- AWS Well-Architected の 6 つの柱
  - 優れた運用効率
  - セキュリティ
  - 信頼性
  - パフォーマンス効率
  - コストの最適化
  - 持続可能性

> AWS Well-Architected Framework
>
> https://aws.amazon.com/jp/architecture/well-architected

### 1.3: 責任共有モデル

- 責任共有モデル

### 1.4: リージョン / AZ / エッジロケーション

- エッジロケーション
  - CDN サービスを届ける拠点

### 1.5: コストの理解

- AWS Pricing Calculator
- AWS Cost Explorer

### 1.6: タグ戦略

- 技術
  - リソース名
  - システム環境
  - etc...
- ビジネス
  - プロジェクト名
  - リソース管理者名
  - etc...
- オートメーション
  - プログラムから参照させる
  - 起動
  - 停止
- コスト配分
  - リソース別のコストをグループ化する

---

## Chapter02: Amazon EC2

### 2.1: EC2 の特徴

### 2.2: AMI

- AMI (Amazon Machine Image)
  - インスタンス構築の設計図

### 2.3: ユーザーデータ

- ユーザーデータ
  - インスタンス初回起動時に実行されるテキストデータ
  - 方法
    - シェルスクリプト
    - cloud-init
- ゴールデンイメージ方式
  - 全ての設定が済んだ AMI から起動する方法
  - 今後、設定を変更する可能性が`低い`場合に有用
- ユーザーデータ方式
  - 空のインスタンスを起動後、ユーザーデータを用いて設定を行う方法
  - 今後、設定を変更する可能性が`高い`場合に有用

### 2.4: インスタンスメタデータ

- インスタンスメタデータ
  - インスタンス内部からのみアクセス可能なインスタンスに関するデータ

### 2.5: インスタンスタイプ

### 2.6: EBS

- EBS (Elastic Block Store)
  - インスタンスにアタッチして利用するブロックストレージサービス
  - windows explorer や Finder で閲覧できるような階層構造を持つデータ
  - FHS (Filesystem Hierarchy Standard) 3.0
    - Linux 系 OS のディレクトリ構成標準規格
- スナップショット
  - EBS でスナップショットを作成することで S3 にバックアップできる (増分バックアップのみ)
  - フルバックアップ
    - 全てのデータを完全に複製する方式
  - 差分バックアップ
    - 最新のフルバックアップ以降の全ての変更を毎回複製する方式
  - 増分バックアップ
    - 前回のバックアップからの差分のみを複製する方式
- クラスタリング
  - 複数台のサーバを連結し、1 つのサーバのように振る舞う技術
  - フェイルオーバークラスタ
    - 稼働中のノードが停止した場合に待機系のノードに処理を引き継がせる
  - 負荷分散クラスタ
    - ロードバランサでリクエストを各サーバに振り分ける
- ブロックストレージ
  - ストレージ -> ボリューム -> ブロックに分割してデータを管理する
  - 低遅延が求められるデータベースシステム、業務システムで利用される
- ファイルストレージ
  - ファイル形式でデータを管理する
  - 階層的なので直感的に運用可能
  - ブロックストレージに比べると、処理速度は劣る
- オブジェクトストレージ
  - 非構造化データ(ドキュメント, 画像, 音声)をオブジェクトとして扱いデータを管理する
  - データアクセスは最も遅い
  - REST API からアクセス
  - 容量の拡張性は高い
  - アプリケーションログなど更新頻度の低い大容量データの保管目的で利用

### 2.7: EFS

- EFS (Elastic File System)
  - フルマネージド型のネットワークファイルストレージサービス
  - オンプレの NAS に相当するサービス
  - 複数インスタンスからの同時アクセスに対応
- ストレージクラス
  - 標準ストレージクラス
    - 複数の AZ に冗長化して保存
  - 標準\_低頻度アクセスストレージクラス
    - 複数の AZ に冗長化して保存
  - 1 ゾーンストレージクラス
    - 1 つの AZ に保存
    - 標準より安価で利用可能
    - ファイルの読み書き毎に課金
  - 1 ゾーン低頻度アクセスストレージクラス
    - 1 つの AZ に保存
    - 標準より安価で利用可能
    - ファイルの読み書き毎に課金

### 2.8: FSx

- サードパーティ製のファイルシステムを提供するフルマネージド型のサービス
- EFS とは異なり、SMB プロトコルもサポートしている
- Amazon FSx for Windows File Server
- Amazon FSx for Lustre

### 2.9: Systems Manager

- AWS リソースやオンプレのインフラストラクチャを管理・制御するためのサービス
- 実現できること
  - リソース状況の可視化
  - 提携作業の実施・自動化
  - アプリの設定管理
- 機能タイプ
  - 高速セットアップ
  - 運用管理
    - Incident Manager
  - アプリ管理
  - 変更管理
  - ノード管理
    - Session Manager
  - 共有リソース

### 2.10: キーペア

- 共通鍵暗号方式の問題点
  - 鍵配送問題
- 公開鍵暗号方式の仕組み
- 暗号アルゴリズム
  - 共通鍵暗号方式
    - 代表的なアルゴリズム
      - AES
    - 暗号化と複合化の処理が軽い
    - 無線 LAN のハイブリッド暗号で今でも使われている
      - 公開鍵暗号で共通鍵をやりとりし、処理自体は共通鍵暗号でデータを暗号化し処理を高速化
  - 公開鍵暗号方式
    - 代表的なアルゴリズム
      - RSA
    - デジタル署名で応用される

### 2.11: 購入方法