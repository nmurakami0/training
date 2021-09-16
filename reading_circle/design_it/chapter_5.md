# 5章 アーキテクチャ上重要な要求を掘り下げる

担当: @y-kaneda

## まとめ

_この章ではソフトウェアに対する要求(誰が何をなぜの「何」の部分)を定義する方法を学ぶ_  
  
### アーキテクチャ上重要な要求(Architecturally Significant Requirement: ASR)
アーキテクチャ構造の選択に強く影響する要求のこと

#### 4つの要求分類について考える
1. 制約
    - 変更できない設計判断。通常は与えられるものだが、選択することもある
    - 制約は選択を制限するものだが同時に問題を単純化し設計を容易にする
    - 逆に制約が厳し過ぎると地獄を見る
    - 制約には技術的なものとビジネス上のものがある
    - 制約は一旦決定してしまうと(100%)交渉不可能となる
2. 品質特性
    - システムが特定の状況でどのように動作するかを特徴付ける、外部から観察できる性質。
    - 何らかのアクションをどれだけうまく行うかを定義する
    - 一般的な品質特性
        - 設計時の性質
        - 実行時の性質
        - 概念上の性質
    - それぞれの品質特性は設計判断によりトレードオフを伴う
    - 品質特性≒非機能要求
        - 非機能要求に対して機能がどう振る舞うかも含まれる
    - 品質特性をシナリオとして記録する
        - ただの言葉・数値としてだけでは無く、シナリオによって品質特性を明確、具体的に表す
        - 品質特性シナリオの要素
            - 刺激(Stimulus)
                - システムに何らかの方法で応答を要求するイベント。トリガーとなるもの
            - 発生源(Source)
                - 刺激の発生元となるもの
            - 成果物(Artifact)
                - 対象となるシステムもしくはその一部の特定コンポーネント
            - 応答(Response)
                - 成果物の刺激に対する結果としての振る舞い
            - 応答測定(Response measure)
                - 応答のシナリオに対する成否判断のための具体的で測定可能な判定基準
                - 自身の経験から潜在的な値を予測するところから初め、ステークホルダーの共感を呼ぶ応答測定を見つける
            - 環境(Environment)
                - システムを取り巻く状況。負荷状態や障害状況等
3. 影響を与える機能要求(influential functional requirement)
    - アーキテクチャにおいて特別な注意を必要とするフィーチャーや機能
        - アーキテクチャを考える上では特別重要視するレベルではない機能もある
    - 価値が高く優先度の高い機能が実装可能でなければアーキテクチャそのものを最初から設計し直さなければならないため、*アーキテクチャキラー*と呼べる
4. その他の影響を及ぼすもの
    - 時間、知識、経験、スキル、社内政治、あなた自身の余計なバイアス、そして意思決定を左右するその他すべてのもの。
    - コンウェイの法則により、チーム組織間の境界がアーキテクチャ要素の境界となる

#### 必要な情報を掘り下げる
- ASR(アーキテクチャ上の重要な要求)は色々なところに隠れている
    - ユーザーストーリーの中
    - マネージャーの要求による暗示
    - 曖昧なステークホルダーの説明
    - プロダクトバックログの中
- ステークホルダーと話をし、情報を掘り下げる
    - ASRを見つけるための手法
        - GQMワークショップ
        - ステークホルダーインタビュー
        - 前提リスト
        - ミニ品質特性ワークショップ
        - インセプションデッキ

#### ASRワークブックを組み立てる
- ASRを特定したらASRワークブックに記録する
- プロジェクト初期に活発に更新され、アーキテクチャが固まっていくにつれ次第に更新されなくなるが、逆に参照される機会が増えていく
- 最終的には実行可能なテストやソースがワークブックの一部に取って代わることがある
- ステークホルダー(関係者)にASRを理解している人が増えれば増えるほどアーキテクチャの見落としは少なくなる

## 分かってないこと

- 特にないです

## ディスカッション

- 5.2.3 について話してみる