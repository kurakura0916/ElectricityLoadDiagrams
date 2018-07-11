# [WIP]ElectricityLoadDiagrams

## 概要
UCIの[ElectricityLoadDiagrams20112014 Data Set](https://archive.ics.uci.edu/ml/datasets/ElectricityLoadDiagrams20112014)を使った教師なし学習を行う。
以下のデータセットの説明からわかる通り、各クライアントの消費電力からクラスタリングを行いクラスタの特徴を把握する。

## データセットの説明

| カラム名 | データ型 | 説明 |
|:---|:---:|---:|
|Unnamed:0 |strings |時間帯（15分単位） |
|MT_001 |integer |クライアントMT_001の消費電力量（kW）|
|MT_002 |integer |クライアントMT_002の消費電力量（kW） |
|MT_003 |integer |クライアントMT_003の消費電力量（kW）  |
|... |integer |クライアントMT_...の消費電力量（kW）  |
|MT_370 |integer |クライアントMT_370の消費電力量（kW）  |

## 環境
Python 3.6.4 :: Anaconda, Inc.

## 作業手順
1. データ型の変換
2. 特徴量の作成
3. 欠損値の処理
4. 次元削減（t-sne）
5. エルボーメソッドによるクラスタ数の決定
6. K-meansによるクラスタリング
7. クラスタ毎の平均と分散び算出
8. 週/時間毎に非線形回帰を行う

## 備忘
- t-sneによる次元削減
  - 高次元データの次元を削減する手法
  - 2点間の近さを確率分布で表す
    - 基準となる点で正規分布を考え、距離を測りたい点が抽出される確率密度を考える。
  - 参考文献
    - https://blog.albert2005.co.jp/2015/12/02/tsne/
