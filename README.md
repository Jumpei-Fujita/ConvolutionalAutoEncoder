# ConvolutionalAutoEncoder

## データセットの作成
今回はtensor-flowのmnist-datasetを用いて畳み込み層を有するAutoEncoderを作成した。
### 1.画像データの標準化
画像データを扱いやすい大きさにするため全てのデータを輝度の最大値255で割ることで0~1の間に丸めた。
### 2.正解データ
今回は訓練データと正解データはほぼ同じものを用いる。<br>
AutoEncoderは入力と出力がなるべく近くなるように学習する。

## モデル構築
![model](https://github.com/Jumpei-Fujita/ConvolutionalAutoEncoder/blob/master/CAE_architecture.png)<br>
モデルの構造は以下の通りである。
出力と訓練データのラベルのMSEを最小にするように学習パラメータの更新を行った。
訓練時に訓練データに傷を入れ、その傷があっても元どおり復元できることを目指した。
最適化手法はAdamを選択した。

## 結果
### 入力画像
![model](https://github.com/Jumpei-Fujita/ConvolutionalAutoEncoder/blob/master/image.png)<br>
### 出力画像
![model](https://github.com/Jumpei-Fujita/ConvolutionalAutoEncoder/blob/master/result.png)
### encoderの出力
![model](https://github.com/Jumpei-Fujita/ConvolutionalAutoEncoder/blob/master/encoded.png)

## コードの実行手順
CAE.ipynbを上から順に実行していく



