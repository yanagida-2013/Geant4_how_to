# Geant4とは
Geant4とは、Cernで開発されている粒子の相互作用をシミュレーションするプログラムです。
類似するものにPhitsやMCNPがあります。

# Geant4の設計思想
Phitsの場合、"すでにコンパイルされている"実行ファイルにインプットファイルを読み込ませる、という形でシミュレーションを実行します。
そのため、ユーザーが検出器やサンプルを規定するときはインプットファイルのみを変更します。

一方でGeant4が提供しているのは実行ファイルではなく、ライブラリ(ツールキット)です。そのため、自分でソースファイルを作成してコンパイルする必要があります。この際に、C++言語で独自の設定を組み込むことができるため、自由度が高くなります。


# Geant4のインストール
Geant4のインストールはかなり骨が折れますが、Windowsにインストールするのはさらに大変です。
LinuxやMacにインストールします。

## 必要な条件
- C++コンパイラはgccの場合4.9以上。clangの場合は???
- cmakeが必要。cmakeのバージョンは???以上

## ダウンロード
[Geant4-Download-Cern](http://geant4.web.cern.ch/geant4/support/download.shtml)

バグが報告されたり、計算方式のアップデートがなされているので最新版をインストールしたほうがいいと思います。

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

Macでインストールする場合は最後の２つが必要でした。


# Geant4のサンプル
サンプルはデフォルトのインストール先の場合、/usr/local/share/Geant4-??-?/examples/の中にあります。

サンプルをベースに自分のシミュレーションの形に変更するのが近道です。

##  barcaでサンプルを試す
### sshでログイン
-Yオプションを忘れずに。
例:
```
ssh yanagida@172.20.???.??? -Y
```

### Geant4の設定ファイルを読み込む
```
source /usr/local/bin/geant.sh
```

### Geant4で使用する核データをJENDL-4.0に変更する
```
export G4NEUTRONHPDATA=/usr/local/share/Geant4-10.1.0/data/JENDL-4.0
```


上の２つは毎回必要になるので、シェルの設定ファイルに書き込んでおくと便利。

設定ファイルは自分のホームフォルダにある.bashrcを使う。このファイルはログイン時に読み込まれる。

例:
```
emacs ~/.bashrc
```


### サンプルを試す
まずはGeant4用のフォルダを作って移動する。
```
mkdir geant4
cd geant4
```
サンプルをコピーしてくる
```
cp -rf /usr/local/share/Geant4-10.1.0/examples/basic/B1 .
```
サンプルの実行ファイルを入れるビルドフォルダを作り、移動する。
```
mkdir B1-build
cd B1-build
```
サンプルをビルドする。
```
cmake ../B1
make
```
サンプルを起動する。
```
./exampleB1
```
起動するとイメージが表示され、対話モードに入る。

ビームを1000発、発射するコマンド
```
/run/BeamOn 1000
```
他にもいろいろとコマンドがある。
イメージの向きを変えたり、放出粒子の種類やエネルギーを変更したりできる。


# Geant4の基本的な使い方

[こちら](http://ikarino99.hatenablog.com/entry/2014/11/10/120243)に簡単にまとめています。
