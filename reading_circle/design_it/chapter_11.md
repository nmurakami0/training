# 11章 アーキテクチャを記述する

担当: @y-kaneda

## まとめ

_正確で習得しやすいソフトウェアアーキテクチャ記述を簡単に作成する方法を学ぶ_  
  
### 全体像を語る
- 全てのアーキテクチャ上の設計判断をコードで表現できるわけではない
- 重要な初期段階ではコードを読めるステークホルダーはほとんどいない
- アーキテクチャ記述が必要な重要な理由は以下の通り
    - **整理する**
        - ソフトウェア構築の際、技術的なものだけではなく人々とも連携する
        - 何がどう連携して動作するか誰もが把握できるようにする必要がある
    - **各ステークホルダー間で共通語を確立する**
        - アーキテクチャ記述は設計の語彙を確立するモデルを、さまざまなステークホルダーが理解できるアイディアへと変換する
        - アーキテクチャ記述はアーキテクチャ上の設計判断のビジネス目標や品質特性への対処を示す
    - **品質特性にスポットライトを当てる**
        - 分かりづらい品質特性を、見たり読んだり話せる形あるものにすることで誰もが思い浮かべられる触感性あるものにできる
    - **考えを明確にする**
        - 書き出すことにより、分かっていること、分かっていると思っていたこと、分からないことが浮き出る
    - **評価できるものを作る**
        - 見たり、触れたり、共有できるものがあれば、変更が容易なうちに設計判断を評価・分析することができる
    - **見せびらかす**
        - 目的・計画・ビジョンを明確に表現することでリーダーシップが発揮できる

### 状況に応じた記述方法を選ぶ
- アーキテクチャ記述に万能なアプローチは無いが、設計判断の変更頻度と共有の必要性の度合いによりいずれかの文書化の方法に決めることができる

#### 部族的な方法によってオーラルヒストリーを作る
- 口承と文化遺産に大きく依存する
- ストーリーテリング、メタファー、雑なスケッチ等
- 迅速で簡単に作成・変更ができるが、共有が困難

#### 共通の方法によって到達範囲をさらに広げる
- より多くの人へと伝わるように記述スタイルを共通の方法に発展させる
- 共通のアーキテクチャ記述方法
    - アーキテクチャ俳句
    - アーキテクチャ上明白なコーディングスタイル
    - アーキテクチャデシジョンレコード(ADR)
    - etc.
- 変更を容易に保ったままで部族的な方法よりも共有を容易にする

#### 必要なときだけ形式的な記述に投資する
- 伝統的なアーキテクチャ記述や形式的モデルを含む
- 膨大な量のドキュメントになる傾向があり、作成により多くの努力が必要とされる
- 形式的モデルはより高い精度と精密さが必要とされる
- まずは部族的な方法 → 共通の方法と進み設計判断を下していき、それらをまとめて従来のドキュメントを作成する

#### 伝統的なソフトウェアアーキテクチャ記述を作成する
- これまでSAD(Software Architecture Description)と言われてきたような記述
- 厳格な形式等があり数十ページに及ぶため、作成するのに時間がかかるが見合うだけの価値はある
- SADはストーリー全体を伝えるためにすべてがまとめられた一つの成果物
- おすすめテンプレート
    - SEI の Views and Beyond テンプレート
    - ISO/IEC/IEEE 42010 の標準テンプレート
- 伝統的なアーキテクチャ記述はすべて共通の基本部分がある
    - 導入と事前情報
    - SADの概要と紹介
    - ステークホルダー、ビジネス目標、アーキテクチャ上重要な要求(ASR)の概要
    - コンテキストビュー
    - 関連ビュー
    - リスク、未解決の質問、今後の課題
    - 付録

### 時間を無駄にするのを避ける
- 変更が困難で共有も難しい記述方法は避ける
    - スライドによるアーキテクチャ記述
- 時間を無駄にしない、優れたアーキテクチャ記述の特徴
    1. 聴衆を念頭に置いて特別に作られている。
    2. アーキテクチャの複数のビューを示している。
    3. 要素とその責務を明確に定義している。
    4. 設計判断についての根拠を説明している。

### 聴衆に配慮する
- アーキテクチャ設計は現実の人間に作用を及ぼす
- 誰のため、何のため、どうやって、を記録したものを必要な人に共有することを意識する
    - どのようなステークホルダーがどのような情報を必要としているのか
- 共感マップ
    - 行動/発言/作るもの/思考 を並べて聴衆がどのような属性を持っているか考える材料にする

#### 理解しやすさに専念する
- 既存の設計用語やドメイン用語等、完全な誤りでない場合は受け取り側が使用している言葉に合わせる
- 難しい言い回しや専門用語は使わない
- UML等、特定の知識が必要とされる記法にこだわらず、凡例を含めた分かりやすい図を使用する
- 読みやすい見栄えを考慮する

### ステークホルダーの関心ごとを中心にビューを構成する
- 人(とその立場)によって興味のある情報は異なる
- ステークホルダーを念頭に置いてビューの構成を考える

#### ビューポイントを確立する
- ビューポイント（Viewpoint）とは、ステークホルダーの特定の関心事に関連するまとまりに従ってアーキテクチャを説明する方法を定義するもの
- 示すべきビューだけでなく、誰に向けたビューなのか、ビューを作成するときに使用する表記法、語彙、規則についても定義する
- ISO/IEC/IEEE 42010：2011規格 の一部

#### カスタムビューポイントを作成する
- おすすめのビューポイントセット
    - SEIのViews and Beyondの枠組み
    - Phillipe Krutchenの4+1ビューモデル
    - RozanksiとWoodsが示したビューポイントとペースパクティブによる方法
    - Simon BrownのC4モデル
- ステークホルダーの特定のニーズを満たすために構成されるビューポイントもある
    - スケーラビリティ、セキュリティ、保守性のビューポイント
        - 特定の品質特性シナリオをどのように満たすかを示す
    - 規制のビューポイント
        - 監査を実施するために必要な情報を提供
    - 学習容易性のビューポイント/チーム受け入れのビューポイント
        - 新規メンバーのアーキテクチャ見通し・速やかな開発への参加を助ける
    - ビジネスインパクトへのビューポイント
        - ビジネス価値にどのように貢献しているかを示す

### 判断の論理的根拠を説明する
- 設計根拠とは、それぞれの設計を決定した理由を説明するもの
- すべての設計判断は性質間のトレードオフがあり、いくつかの論理的思考プロセスを通して結論付けられる
- 判断根拠が理解されれば後続の設計者は設計の意図を理解でき、将来的にもアーキテクチャの一貫性が維持される

#### 選ばなかった道を説明する
- 選ばなかった選択肢とその理由を列挙する方法
- チームとして話し合った議論もきちんと記録しておく

## 分かってないこと

- 特にないです

## ディスカッション

- 何かプロジェクトで選ばなかったものとその理由を話してみる