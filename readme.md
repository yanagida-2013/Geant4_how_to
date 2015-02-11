# Geant4とは
Geant4とは、Cernで開発されている粒子の相互作用をシミュレーションするプログラムです。
類似するものにPhitsやMCNPがあります。Geant4はこれらに比べ、自由度が高い一方、難易度が高い傾向にあります。

# Geant4の設計思想
Phitsの場合、"すでにコンパイルされている"実行ファイルにインプットファイルを読み込ませる、という形でシミュレーションを実行します。
そのため、ユーザーが検出器やサンプルを規定するときはインプットファイルのみを変更します。

一方でGeant4が提供しているのは実行ファイルではなく、ライブラリ(ツールキット)です。そのため、自分でソースファイルを作成してコンパイルする必要があります。この際に、C++言語で独自の設定を組み込むことができるため、非常に自由度が高くなります。


# Geant4のインストール
Geant4のインストールはかなり骨が折れますが、Windowsにインストールするのはさらに大変です。
LinuxやMacにインストールします。

## 必要な条件
- C++コンパイラはgccの場合4.9以上。clangの場合は???
- cmakeが必要。cmakeのバージョンは???以上

## ダウンロード
[Geant4-Download-Cern](http://geant4.web.cern.ch/geant4/support/download.shtml)

まだまだバグが報告されたり、計算方式のアップデートがなされているので最新版をインストールしたほうがいいと思います。

## インストール
インストールする際にはオプションを指定します。

[Installation guide](http://geant4.web.cern.ch/geant4/UserDocumentation/UsersGuides/InstallationGuide/html/ch01.html)

重要なオプションは以下になります。

* -DGEANT4_BUILD_MULTITHREADED=ON
* -DGEANT4_INSTALL_DATA=ON
* -DGEANT4_USE_OPENGL_X11=ON
* -DGEANT4_INSTALL_DATA_TIMEOUT=9000
* -DCMAKE_C_COMPILER=/usr/bin/clang
* -DCMAKE_CXX_COMPILER=/usr/bin/clang++

Macでインストールする場合は最後の２つが必要です。


# Geant4のサンプル
サンプルはデフォルトのインストール先の場合、/usr/local/share/Geant4-??-?/examples/の中にあります。

サンプルをベースに自分のシミュレーションの形に変更するのが近道です。

# Geant4の基本的な使い方

[僕のブログ](http://ikarino99.hatenablog.com/entry/2014/11/10/120243)に簡単にまとめています。
