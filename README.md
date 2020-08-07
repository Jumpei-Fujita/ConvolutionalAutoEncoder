# ConvolutionalAutoEncoder

## データセットの作成
今回はtensor-flowのmnist-datasetを用いて畳み込み層を有するAutoEncoderを作成した。
### 1.画像データの標準化
画像データを扱いやすい大きさにするため全てのデータを輝度の最大値255で割ることで0~1の間に丸めた。
### 2.正解データ
今回は訓練データと正解データはほぼ同じものを用いる。<br>
AutoEncoderは入力と出力がなるべく近くなるように学習する。

## モデル構築
![model](https://github.com/Jumpei-Fujita/kadai2/blob/master/dentsu_neuralnet.png)<br>
今回はニューラルネットワークにより学習を行うことで回帰を行った。
ニューロン数は上の画像の通りである。
出力と訓練データのラベルのMSEを最小にするように学習パラメータの更新を行った。
最適化手法はSGDを選択し、ハイパーパラメータとしてlearning rate、weight decayの設定を訓練データ、検証用データの評価を考慮して行った。

## テスト結果
### 1.テスト用データに対するMAE, RMSE, MER(平均誤差率)
|learning rate|weight decay|MAE|RMSE|MER|R2スコア|
|:--|:--|:--|:--|:--|:--|
|0.1|10^(-8)|135447.69|241691.66|24%|0.6078636|
### 学習の様子
![model](https://github.com/Jumpei-Fujita/kadai2/blob/master/glaph.png)

## コードの実行手順
price.ipynbを上から順に実行していく



