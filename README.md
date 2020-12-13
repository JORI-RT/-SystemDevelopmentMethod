# SystemDevelopmentMethod
DDDとICONIXとアジャイルを複合したシステム開発構想

# 自分が想定している開発戦略
* コンテキスト間の分析にはDDDのBC、コンテキストマップを利用
* 開発対象の要求ー＞分析ー＞予備設計までは、ICONIXを利用
* 実装、テスト、結合テストはアジャイル手法を利用（TDD,CI/CD、バックログがユースケースになるイメージ,
* ユースケースをそのまま受け入れ条件にする）
* 見積もりは予備設計で作成したユースケースをもとに行う
* アーキテクチャはDDDの戦術的モデリングを利用（ヘキサゴナルアーキ、集約、エンティティ、リポジトリ、値オブジェクト、サービス）
* フィードバックはイテレーションごとにいれる
* メンテ対象ドキュメントは、ユースケース、ドメインモデル、状態遷移図、コンテキストマップ、（ロバストネス図？）のみ
* コンテキスト間の結合はDDDのコンテキスト間の結合を利用
* テスト戦略は？？？？
* 運用を意識した設計（ユースケース作成時にある態度、非機能要件、運用の要件を決めて、その後のイテレーションで改善）

# 開発手法
## 分析フェーズ
### 要求分析
業務側側から何がやりたいか、やりたくないか要求をだしてもらう
* output
asis tobe資料
### コンテキストマップの作成
開発対象のドメインと他ドメインとの関係を明らかにする(フロント、バック含め)
* input   
既存の業務、システム、要求一覧、業務との会話 
* output
コンテキストマップ
### ドメインモデリング(BCの概要を記載)
* 利用用途
プロジェクトの語彙として使う
* input   
既存の業務、システム、要求一覧、業務との会話  
* output
概要クラス図
### ユースケース図、ユースケース記述作成
* 利用用途
プロジェクトのスコープの確定につかう、システムとユーザのインタラクションを記載
* input   
既存の業務、システム、要求一覧、業務との会話 、概要クラス図
* output
ユースケース図、ユースケース記述

## 設計フェーズ
### 状態遷移図を作成
* 利用用途
プロジェクトの最重要オブジェクトである、注文の状態の推移を記載
* input   
ユースケース、ドメインモデル
* output
状態遷移図
### アーキテクチャの決定
* 利用用途
プロジェクトの技術的なアーキテクチャをだいたい固める
* input   
コンサルの知識
* output
プロジェウとの雛形、CI・CDパイプライン、インフラ,
### 概算スコープの確定
* 利用用途
プロジェクトのスコープを予算から確定する
* input   
ユースケース
* output
減らしたユースケース

## 実装ー＞テストフェーズ
### 実装ー＞テスト
ユースケースをバックログにしたタスク分解、機能テスト、非機能テスト、詳細設計、実装、単体テスト、結合テストの実施
受け入れを必ずやる
### ある程度の頻度でリリースを実施し、運用性の確認を実施