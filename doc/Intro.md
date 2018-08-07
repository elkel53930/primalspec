PrimalSpecでの形式仕様記述駆動開発
===================================

この文書について
-----------------

* 某所用の資料です
* 読者はCが書ける人を想定しています
* 目標はコレを読んだ人が
    * PrimaslSpecでソフトウェアの仕様を記述すべきかどうか議論出来るようになること
    * PrimaslSpecで書かれた記述が理解出来ること


仕様の定義について
-------------------

* SW業界では、XX要求、要件、XX仕様、XX設計、実装という言葉をよく耳にしますが、それらの具体的な定義は組織や人によって様々です。
* ただ、規格や知識体系は存在していて、個人的に洗練されてると感じているのは[SWEBOK](http://swebokwiki.org/)です。
    * 第一、ニ章を読むだけで、要求、機能要求、非機能要求、仕様(SRS)、設計、verification & validation 等についての定義や雰囲気が分かるかと思います。
* とかいいつつも、ここではシンプルにシステム利用者から観測される振る舞いを仕様と呼ぶことにします。


なぜ、設計・実装前に仕様を書くのか？
--------------------------------------

まず、私が強調したい点は以下の１点です。

* 仕様や要求という抽象度が高いレイヤーであっても、いざ書いてみると様々な気づきが得られる
    * おや？思ったよりも難しそうだゾ
    * 具体的にどんなもの作ればいいんだっけ？どうやって検証するんだっけ？
    * 仕様レベルの間違いに気付ける(欠陥の中でこういった間違いの割合が多いことや、それらが手戻りになって開発工数伸びる話は書籍等でよく見かけます)

似たような効果があるものとしてプロトタイピングもありますが、こちらは機能の一部だけを動作するモノを実際に作ってみて顧客からのフィードバックを求めたり、技術的な仮説を検証したりするのが主な目的です。

一方、Karl E. Wiegers の"ソフトウェア要求"という本の第一章では何故設計・開発前に仕様を書くのかについて分かりやすく解説しています。
私見になりますが、その中でも以下の３つがビジネス面において最も重要なメリットと言えるかと思います。

1. 開発工数の増大防止
2. 見積り精度の向上
3. 顧客満足度の向上

また、仕様変更時においても、抽象度が高い分ソースコードを読むよりお手軽に修正範囲についてチェック出来ます。
もちろん結局はコードも見る必要はありますが、コードだけだと抽象度が低くボリュームが大きくなり見落としが怖いと筆者は感じてしまいます・・・


自然言語での記述のデメリット
-------------------------

思いつく範囲で挙げてみます。

* 複数人で記述する場合、口調や名前の統一やらが大変(チェックも大変)
* あるモノに対して皆が好き勝手名前をつけ始めると検索すらまともに出来なくなる
* 意味が一つに定まらない場合がある
* 行間を読まないといけない場合がある
* 記述した内容の整合性のチェックも難しい(結局は形式的にモデル作ることに・・・)
* 抽象化し辛くて、ボイラープレートが多くなる傾向がある
* なんとなく書けて、なんとなく読めて、なんとなく理解した気になってしまう
* 文法以外は機械チェックがし辛い


形式的な記述
-------------------------

形式的にモデルを記述する為のツールや言語は色々あって、それぞれ向き不向きがあったりするようです。

最もシンプルで馴染み深いものの１つは状態遷移モデルでしょう。
ここでいう状態遷移モデルの記述とは、状態遷移図もしくは状態集合、入力集合、出力集合、遷移関数、出力関数の組を書き下すことを指します。

しかし、状態遷移モデルは規模が大きくなると、記述がそもそも大変だったり読み辛かったりします。
この問題を解決する１つの手段としてCSPがあります。これは並行プロセスを記述する為に作られたものですが、状態遷移の記述にも適しています。

PrimalSpecの書き方
-------------------

* README.mdを参照
* HaskellについてはIntroductionforCProgrammer.md を参照

おわりに
-----------

では、以下について議論しましょう

1. 設計・開発前に仕様は書くべきか？
1. 仕様は何を使ってどう書くべきか？自然言語は使うべきか？
