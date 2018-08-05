primalspec
============

原始的な形式仕様記述言語 (Haskell eDSL)

特徴
-------

1. 状態遷移モデルを直接エンコードせず、CSPライクな記法によりコンパクトかつ直感的な記述が可能
    * VDMのstのような陰関数の記述も行える

1. イベント列を指定することで記述した内容についての振る舞いが確認出来る
    * 太古のソルバ(人間)を使って陰関数にも対応可能
    * 仕様に対するユースケース・テストケースの記述としても使える

1. ユーザーとシステムという２つのプロセスの並行性しか想定していない
    * 内部選択・隠蔽・リネーム・インターフェース並行合成はサポートしていない。従って、非決定性もサポートしていない

1. モデル検査機ではない
    * 網羅的な検査機能は提供しない
    * デッドロック・ライブロック・詳細化関係についての機能も提供しない

作った理由
------------

* 無料でビジネスにも使えるCSPライクなツールが見つからなかった(勉強用なら無料でFDR4が使える)


