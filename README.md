# portfolio
saikiRA1011が今までに作った作品・製品をまとめたものです。

## 分子通信シミュレータ
学部・大学院で研究開発をしている分子通信シミュレータです。シミュレータとしての汎用性とシミュレーションの高速化に着目し、多様なシミュレーションをより高速に実行することを目的としています。

現在は細胞間相互作用、細胞の成長・分裂・死滅モデルの他、シミュレーションで必要となる様々なパラメータ(細胞の個数、シミュレーションで考えるフィールドの大きさ、利用する数値計算アルゴリズムなど)をユーザ側で定義することができます。
また複数種類の細胞を定義することで、より複雑なモデルを実行することもできます。

シミュレータのメイン部分はC++で書かれており、付属しているビジュアライザはPython3を用いています。

高速化用アルゴリズムとOpenMPを用いて1シミュレーションステップあたりの速度を向上させており、またシミュレーションの刻み幅に応じて数値計算アルゴリズムを変更することができます。

推奨OSはMac OS、コンパイラはgcc(C++20が使えるバージョン)です。また別途[yaml-cpp](https://github.com/jbeder/yaml-cpp)のインストールが必要です。

リンク：https://github.com/saikiRA1011/CellNetworkShapeSimulation

![シミュレーション例](https://github.com/saikiRA1011/CellNetworkShapeSimulation/blob/main/readme_img/sim.gif "シミュレーション例")

## マッピングラジコン
論理回路の実習授業における発表用作品として制作したラジコンです。

ラジコン側はArduino(C++)で制御し、PC側はProcessing3(Java)で作成した地図表示兼通信用アプリケーションを用います。
通信はBluetoothを用いた双方向の無線通信です。

ユーザがPCのキーボードを用いてラジコンを操作することにより、最終的に周囲環境の障害物をマッピングした地図が作成されます。

ラジコン側は6軸センサ(加速度・ジャイロ)と距離センサ(超音波式)、温度・湿度センサが搭載されており、そこから得られたデータをPC側へ送信します。
またデータを受け取ったPC側クライアントアプリはそれらのデータからラジコンの位置と方向、障害物の位置を計算し、アプリ上に描画します。
PC側からはラジコンへキーボードの入力状況(ラジコンの操作情報)を出力し、ラジコン側は受け取ったデータに応じてモータを制御します。

温度データは距離センサデータの補正に用いるため、Arduino側であらかじめ補正してから距離データのみを送信する方法と両方のデータを送信しPC側で補正をおこなう方法の2通りが考えられますが、Bluetoothの通信速度と
Arduinoの処理クロック周波数を考え、両方のデータを送信する方法をとっています。

リンク：https://github.com/saikiRA1011/Mappingcon

## popipo_s_adventure
ピンク色のキャラクターを操作してゴールまで導くアクションゲームです。Processing3(Java)で記述されています。

もともと授業課題として制作しており、その後授業内評価が好評だったこともあり大学祭での展示のため攻撃機能やステージの追加を追加しました。
ただし最新版のプログラムを紛失しており、リンク先にアップロードされているものは授業課題で提出したプログラムにバグ修正を加えただけのものになっています。

リンク：https://github.com/saikiRA1011/popipo_s_adventure

![popipoタイトル画面](https://github.com/saikiRA1011/popipo_s_adventure/blob/main/thumbnail/thumbnail.png "タイトル画面")
タイトル画面はAdventureのつづりを間違えています。

![popipoプレイ画面](https://github.com/saikiRA1011/popipo_s_adventure/blob/main/thumbnail/play.png "プレイ画面")

## twonake
2匹のヘビを同時に操作するヘビゲームです。大学祭での展示のために作成しました。

[OpenSiv3D](https://github.com/Siv3D/OpenSiv3D)とC++によって記述されており、実行推奨環境はWindows + Visual Studioです。

リンク：https://github.com/saikiRA1011/twonake

![twonakeゲーム画面](https://github.com/saikiRA1011/twonake/blob/master/twonake/App/image/thumbnail.png "ゲーム画面")
