
# 12章 アーキテクチャに通知表をつける

担当: @koushisa

## まとめ

_アーキテクチャを評価する方法を学ぶ_  
  
### アーキテクチャ評価

- 評価の目的
  - チームへの教育
  - 設計判断の良し悪しを判断する
  - 今後のリスク軽減・改善
- 評価の中で学ぶべきこと
  - アーキテクチャはどの程度良いか？
  - アーキテクチャはどのように良いか？
- アーキテクチャを評価する際にアーキテクチャ上重要な要求（ASR）についてわかっていることを利用する

### 設計をテストする

- 全体を最後に一度に評価するのではなく、領域を分けて小さい範囲で、早い段階で頻繁に実施していく
  - 必要なもの
    -  タンジブルな設計
    -  ステークホルダの視点から見た「より良い」または「悪い」を定義したルーブリック（表）
    -  レビュアーがインサイトを生む手助けをするための計画
- タンジブルな設計
  - アーキテクチャをタンジブルにする方法はいくらでもある、聴衆により手法を選択する
    - コードを書く、ホワイトボード、作図アプリケーション、プレゼンテーション、ユーティリティツリー、 etc...
    - 自分達に合う手法で、2章で学んだ理解、探求、作成、評価のサイクルをASRの理解に向けて回していく
      - 評価のコンテキストを合わせるために品質特性に関連するビューを準備しておく
    - コラム(lpek Ozkaya)
      - アーキテクチャの第一歩は、要素感の関係をよりよく理解すること
      - 図に描かれる箱よりも、箱同士を線でつなぐ関連性にも目を向けよう
- デザインルーブリック
  - 観点と尺度（評価）を定義する表
    - 観点は、設計成果物を評価するために使用する特性
    - 尺度は、特性を評価する段階度（通常は数値で表す）
  - 優れたルーブリック
    - 観点
      - 重要かつ不可欠な詳細しか含まない
      - それぞれの観点が重複していない
      - 観点を評価するためのデータがある
      - 観点が明確
    - 尺度
      - 改善が必要、良い、とても良い、最も良いを最低限定義する
      - レビュアーの数や目的によって増減させる
- インサイトを生む
  - 設計がASRを満たしているかをレビュアーが意見するための使うもの
  - ルーブリックの回答からリスク、不確実性、技術的負債などの潜在的な課題をあぶり出す

### 評価ワークショップを開く

- 目標はアーキテクチャを評価するのに必要なデータを集めて分析すること
- 評価の準備をする
  - 評価の目標を決定し、必要な成果物を準備する(表 12-3に例)
- レビュアーに伝える
  - システムのコンテキスト、ASR、レビュー中の成果物や背景情報を伝える
- 評価をファシリテートする
  - アクティビティ
    - シナリオウォークスルー、質問ー意見ー懸念、リスクストーミング、スケッチして比較 etc...
    - 多くの場合はシナリオウォークスルー(アクティビティ37)が基本的で信頼性が高い
- データを分析し結論を導く
  - 評価から得たインサイトを使い、今後のリスクと未解決の問題を探す
    - コラム(金字塔：アーキテクチャトレードオフ分析法)

### 早くから評価を始め、頻繁に継続的に評価する

- 評価ピラミッド
  - 評価のスコープを3つに分けることでテストの実行、保守のバランスを取る
    - 深い評価
      - システム全体とASRの相互作用
    - 対象を絞った評価
      - 設計判断、コンポーネント
    - クイックチェック
      - 単体テスト、コードレビュー
- 評価を網羅するための課題
  - リスク
    - 発生する可能があるが、まだ発生していないもの
    - 軽減するか、受け入れることを選択する
  - 未知のこと
    - ASRを満たしているかを判断するだけの十分な情報がない課題
    - さらなる調査が必要
  - 問題
    - すでに起きている悪いこと
    - 修正するか、受け入れる
  - 理解のずれ
    - チーム内の認識のずれ
    - 急速に進化するアーキテクチャではよく起こる
    - 教育を通じて対処する
  - アーキテクチャの新色
    - アーキテクチャと実装との間に出てくるギャップ
    - コードやドキュメントの細部に定期的に注意を払う
  - 状況の横滑り
    - 設計判断を下したあとでコンテキストが変わってしまった
    - ビジネス目標、ASRを時折見直すことで対処する
- 低セレモニーな評価方法から始める
  - セレモニーの種類
    - 高セレモニー
      - 形式的な決まりごとで満ちており、コストが高い
      - 繰り返しが容易で、一貫した結果を生みやすい
    - 低セレモニー
      - 形式的な決まりごとがなく、コストが低い
      - 範囲が狭く、矛盾する結果を生みやすい
  - 低セレモニーな評価方法から始めることでチームのアーキテクチャ思考を強化する
    - それぞれが設計判断を下すことに挑戦する文化を築きやすい
    - 低セレモニーに慣れたら高セレモニーな評価に挑戦し、深い評価へ導く

## 分かってないこと

- 特にないです

## ディスカッション

- 最近のプロジェクトのアーキテクチャについて、7個以上の質問を書き留めよう（大変そうですが）