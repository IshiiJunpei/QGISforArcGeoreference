# 紙地図をQGISで使う

## この資料について

本資料は2018年9月19日に行われた奈良文化財研究所「遺跡情報記録課程」の「GIS演習」で使用した解説資料です。

## マスターすること

- ジオリファレンサーを使って紙図面に座標を与える。
- 変換方法やリサンプリングについて知る。


## ドキュメント

- [配布資料](https://github.com/IshiiJunpei/QGISforArcGeoreference/blob/master/030QGIS%E3%81%A7%E5%B9%BE%E4%BD%95%E8%A3%9C%E6%AD%A3.pdf)

-  [スライド](https://IshiiJunpei.github.io/QGISforArcGeoreference)

# 紙地図をGISで使う

Created by Ishii Junpei ( [@ishiijunpei](https://twitter.com/ishiijunpei))


## 作業の内容

- QGISジオリファレンサーを使う
- 図面に座標を与える
- 背景図から座標を取得する

---
ラスタ→ジオリファレンサー→ジオリファレンサー

<img src="02.png" width=90%>


ファイル→ラスタを開く

<img src="03.png" width=70%>

---
### 端点測量図の読み込み

<img src="04.png" width=90%>

- 適度に拡大して→既知の座標点へズーム
- ポイントの追加

<img src="05.png" width=70%>

- グリッド交点でクリック
- 交点座標を入力

<img src="06.png" width=70%>

---
- 同一地点から座標を自動取得
- ポイントの追加→マップキャンパスより

<img src="07.png" width=70%>

同一地点をクリック

<img src="08.png" width=70%>

座標を自動取得

<img src="09.png" width=70%>


4点の座標を取得

<img src="10.png" width=90%>

---
設定→変換の設定

<img src="11.png" width=70%>

変換タイプ→シンプレートスプライン（線形でもOK）

<img src="12-1.png" width=50%>

リサンプリング方法→線形

<img src="12-2.png" width=50%>

---
### 変換タイプ

迷ったら、「シンプレートスプライン」

- 線形
- ヘルマート
- 多項式1
- 多項式1
- 多項式1
- シンプレートスプライン
- 投影変換

うまくいかない場合は「線形」で試してください。


### リサンプリング方法

迷ったら、「線形」

- 最近傍
- 線形
- キュービック
- キュービックスプライン
- ランチョシュ

ピクセルの歪みを補完する手法


### リサンプリング方法

- 離散的なデータ　最近傍（統計的な変化がない）
- 航空写真　　　　キュービック（滑らかな結果）

<img src="12-3.png" width=50%>

---
### 変換先SRS

- 「フィルター」に「30171」と入力
- Tokyo / Japan Plane Rectanglur CS11 EPSG:30171

<img src="13.png" width=60%>

### 測地系と座標系、投影系

- 日本測地系（Tokyo Datam）
	- 緯度経度系
	- 平面直角座標系
	- ユニバーサルトランスバースメルカトルグリッド
- 世界測地系（JGD2000）
	- 緯度経度系
	- 平面直角座標系
	- ユニバーサルトランスバースメルカトルグリッド 
- WGS84

---
出力ファイルを選択

<img src="12-4.png" width=50%>

ファイル名を附けて保存

<img src="14.png" width=90%>

ファイル→ジオリファレンスの開始

<img src="15.png" width=90%>

---
### 幾何補正された測量図

<img src="16.png" width=90%>

---
### 現場とGISをつなぐ基本操作

- 幾何補正は現場図面をGISに取り込む基本操作
- 紙図面、航空写真、古絵図

### 昭和23年米軍撮影航空写真

<img src="17.png" width=90%>

### 小学校4年生「昔のまち探検」

<img src="17-2.png" width=90%>

### 松前城線図

<img src="18.png" width=90%>
（背景地図はOpenStreetMapを使用）

---
### 測量図のデジタル化

測量図面はスキャンデータが望ましいが、大型のスキャナがなければ撮影図版で対応することも可能です。

<img src="19.jpg" width=90%>

### 撮影データの幾何補正

撮影された画像データを幾何補正した場合、スキャナデータよりも精度は落ちます。用途に応じてデジタル化の手法を検討してください。

<img src="20.png" width=90%>

