# BrainPadAdventCalendar2018_Day23th
リサーチクエスチョン


- 色々出ているけど、差はあるの？
- 結局MLシステム開発&保守運用者は何が楽になると嬉しいの？
- どこからどこまでは既存のツールでおｋ？どこからはカスタマイズが必要？


- なんのための機械学習基盤?
- 普通のシステム基盤と何が違う？
- どのような技術&ツールを組み合わせて実現？
- 関連のある基盤は？


# 機械学習基盤の分類
- [クックパッドの機械学習基盤](https://speakerdeck.com/ayemos/machine-learning-platform-at-cookpad-2018?slide=7)

-　[リクルートRS、Jypyterだけで機械学習を実サービスに展開できる基盤](https://engineer.recruit-lifestyle.co.jp/techblog/2018-10-04-ml-platform/)

- [PFN:Kubernetesによる機械学習基盤への挑戦](https://www.slideshare.net/pfi/kubernetes-125013757)
  - 大量の機械学習Jobをさばきたい
  - セキュリティ・プライバシー機能が充実
  - スケジューリングの機能が充実
  - 柔軟かつ用意な拡張が可能
    - よってKubernetes
  - 自由度の担保
    - 様々なリテラシ
    - 特定のツールでロックインしない
    - ユーザーごとの環境、コンフィデンシャルな案件
 - [オートモーティブ事業におけるMLOPs](https://www.slideshare.net/ShotaSuzuki2/mlops-shibuyasynapse-4-125602323)

  
- https://github.com/Azure/kubeflow-labs
- FBLearner
- 
  
  
  
  
  # 機械学習基盤にて実施すべき内容
  https://speakerdeck.com/ayemos
  
  
## 規模によって使うべきツール違うよね？
  - SageMakerでjupytetrnotebook立ち上げる
  - SageMakerで開発、学習、推論までやろうと思えばすべてdキル
  - 少人数でMLプロジェクトに取り組むときに有用だが、大規模で色々なスキルを持った人がいる場合では必要性が薄く感じる
  - SpotInstanceが使えないからGPU処理コストかさむ
  − SageMaker独自の扱いを覚える必要がある
  - 推論：モデル作成者以外にソフトウェアエンジニアがいるのでわざわざSageMakerのものを使う必要がない
  - SageMaker+Airflowなどを使った学習パイプラインの整備
  - データセットの管理
  − 実験管理周りの効率化


## 必要な点
- 結局ユーザーに使ってもらわないと意味がない
  - 軽いプロダクトをリリースしてモデル精度はもちろん、業務プロセスにのるのか、UX全体を確認してもらう必要がある
  - Webアプリやインフラ全体を維持してくれるエンジニアが潤沢にいない場合もある
    - Web系企業と、そうでな企業でエンジニアが潤沢にいない場合では、モデルメンテ、システムメンテに使えるリソースに差がある
  - DeNAの記事、freeeの記事

- Deployまではオッケー、けどメンテし続けなければいけない
  - モデル作った人が現場を離れなければいけない可能性もある
  - いつ、だれが、どんな手順で実施したかがわかる、ログが残っている
    - ログとして残しておきたいもの
      -　どのデータ、どのハイパラで、どの指標にたいしてどの程度だったのか。モデル選択に使う指標は1つだとしても、挙動把握のために複数の指標を使うことはよくある
  -　機能
    - モデルのデプロイ簡単
    - サービング、オートスケール欲しい
    - 実験(ハイパラ探索や特徴選択など、学習と評価の過程)ログの保存と一覧性

- 小さく始める&使い続けるために便利なツール達
  - mlflow&airflow
  - SageMaker&Airflow
 - 機能面を比較する。
 余力があればAirflow+SageMaker触ってみる


## やったこと
"""
export SLUGIFY_USES_TEXT_UNIDECODE=yes
pip install appach-airflow
"""
→だめだ、airflowのインポートができん。
