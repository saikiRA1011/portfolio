# portfolio
今までに作った作品・製品をまとめたものです。

# 研究
## 分子通信シミュレータ
学部・大学院で研究開発をしている分子通信シミュレータです。シミュレータとしての汎用性とシミュレーションの高速化に着目し、多様なシミュレーションをより高速に実行することを目的としています。

現在は細胞間相互作用、細胞の成長・分裂・死滅モデルの他、シミュレーションで必要となる様々なパラメータ(細胞の個数、シミュレーションで考えるフィールドの大きさ、利用する数値計算アルゴリズムなど)をユーザ側で定義することができます。
また複数種類の細胞を定義することで、より複雑なモデルを実行することもできます。

シミュレータのメイン部分はC++で書かれており、付属しているビジュアライザはPython3を用いています。

高速化用アルゴリズムとOpenMPを用いて1シミュレーションステップあたりの速度を向上させており、またシミュレーションの刻み幅に応じて数値計算アルゴリズムを変更することができます。

推奨OSはMac OS、コンパイラはgcc(C++20が使えるバージョン)です。また別途[yaml-cpp](https://github.com/jbeder/yaml-cpp)のインストールが必要です。

リンク：https://github.com/saikiRA1011/CellNetworkShapeSimulation

![シミュレーション例](https://github.com/saikiRA1011/CellNetworkShapeSimulation/blob/main/readme_img/sim.gif "シミュレーション例")

## 論文・口頭発表
- 国際学会論文
  - (査読有り) "Design and Implementation of a Multicellular Molecular Communication Simulator", SCIS&ISIS 2022, 第1著者
  - (査読有り) "Modeling and simulations of vascular-like structure formation of cancer cells", ISMICT 2022, 第2著者
  - (口頭発表 査読なし) "Design and Implementation of a General-purpose Multicellular Molecular Communication Simulator", BICT 2023, 第1著者
  - (査読中) "Design and Implementation of a General-purpose Multicellular Molecular Communication Simulator", APCM23, 第2著者

- 国内学会論文
  - (口頭発表 査読なし 発表予定) "Barnes-Hut アルゴリズムによる分子通信シミュレーションの高速化", Society2023, 第2著者

# 授業課題
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

パーツ単位では正常に動作したものの、はんだ付け不良のため完成したラジコンはモータの不正な挙動によって正常に動作しませんでした。

リンク：https://github.com/saikiRA1011/Mappingcon

## popipo_s_adventure
ピンク色のキャラクターを操作してゴールまで導くアクションゲームです。Processing3(Java)で記述されています。

Processingでは図形や画像描画、ウィンドウ描画用の関数が用意されており、それ以外の部分(地面や敵、ゴールとの当たり判定、キャラクターのアニメーション用プログラム)は完全に1から自力で書きました。

もともと授業課題として制作しており、その後授業内評価で優秀作品として紹介されたこともあり大学祭での展示のため攻撃機能やステージの追加を追加しました。
ただし最新版のプログラムを紛失しており、リンク先にアップロードされているものは授業課題で提出したプログラムにバグ修正を加えただけのものになっています。

リンク：https://github.com/saikiRA1011/popipo_s_adventure

![popipoタイトル画面](https://github.com/saikiRA1011/popipo_s_adventure/blob/main/thumbnail/thumbnail.png "タイトル画面")
タイトル画面はAdventureのつづりを間違えています。

![popipoプレイ画面](https://github.com/saikiRA1011/popipo_s_adventure/blob/main/thumbnail/play.png "プレイ画面")

# サークル活動
## popipo_s_adventure
上記の内容と同じ。

## twonake
2匹のヘビを同時に操作するヘビゲームです。大学祭での展示のために作成しました。

[OpenSiv3D](https://github.com/Siv3D/OpenSiv3D)とC++によって記述されており、実行推奨環境はWindows + Visual Studioです。

リンク：https://github.com/saikiRA1011/twonake

![twonakeゲーム画面](https://github.com/saikiRA1011/twonake/blob/master/twonake/App/image/thumbnail.png "ゲーム画面")

# アルバイトでの開発
## webシステムの開発(未公開)
Pythonを用いたリアルタイムセンサデータの加工・データベースへの格納をおこなうシステムや、web上で動作するビジュアライザの開発をおこないました。ビジュアライザはFlaskを用いてwebサーバ上で動作させ、指定期間中のセンサデータ可視化と基礎統計量の計算、一定値以上(以下)のデータの抜き出しといった機能を実装しました。  
開発プロジェクトには複数人が参加しており、GitLabを用いてプロジェクト・タスクを管理しました。

## センサデータのリアルタイム処理プログラム作成(未公開)
複数のセンサから受信したデータをリアルタイムに処理し、計算結果に対応する表示をおこなうGUIアプリケーションを開発しました。

## モータ制御
Arduinoを用いたモータ制御システムを開発し、トランジスタ等の電子素子を用いて2相バイポーラステッピングモータ用のドライバ回路を作成し、その制御用プログラムを実装しました。

# 趣味・独学での開発事例
## TRPG自動運営bot (友人との共同開発のため未公開)
現在、LINE APIとOpenAI APIを用いたTRPG(テーブルゲームの一種)の自動ゲーム運営botを友人と共同開発しています。botはGoogle Apps Script(GAS)で記述されており、現在はゲームの運営とプロンプトの初期化、擬似的なダイスロール機能が実装されています。

Open APIを用いる際の問題点として、テキスト生成の遅さや、トークン長の制限、リクエスト頻度の制限といったものがあります。このbotではトークン長の制限に対応するため、保存しているプロンプトを定期的にGPTモデルに要約させることにより過去のプロンプトの文章量を減らし、送信するトークン長を削減しています。

現在はデモンストレーション用としてGASを用いてサービスをデプロイしていますが、最終的にはPythonプログラム等をサーバ上で動作させることでbotを運営したいと考えています。
