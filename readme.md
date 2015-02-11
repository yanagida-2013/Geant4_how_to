# Geant4とは
Geant4とは、Cernで開発されている粒子の相互作用をシミュレーションするプログラムです。
類似するものにPhitsやMCNPがあります。Geant4はこれらに比べ、自由度が高い一方、難易度が高い傾向にあります。

# Geant4の概要
Phitsの場合、"すでにコンパイルされている"実行ファイルにインプットファイルを読み込ませる、という形でシミュレーションを実行します。
そのため、ユーザーが検出器やサンプルを規定するときはインプットファイルのみを変更します。

一方でGeant4が提供しているのは実行ファイルではなく、ライブラリ(ツールキット)です。そのため、自分でソースファイルを作成してコンパイルする必要があります。この際に、C++言語で独自の設定を組み込むことができるため、非常に自由度が高くなります。


# Geant4のインストール
Geant4のインストールはかなり骨が折れますが、Windowsにインストールするのはさらに大変です。
LinuxやMacにインストールします。

## ダウンロード
[Geant4-Download-Cern](http://geant4.web.cern.ch/geant4/support/download.shtml)
まだまだバグが報告されたり、計算方式のアップデートがなされているので最新版をインストールしたほうがいいと思います。

## インストール
インストールする際にはオプションを指定します。
[Installation guide](http://geant4.web.cern.ch/geant4/UserDocumentation/UsersGuides/InstallationGuide/html/ch01.html)


書きかけ
