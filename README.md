<center><h1>文章自動分類</h1></center>
----
痞客邦為華文區最大的部落格服務網站，擁有眾多閱讀者及大量的優質文章。而相關文章自動分類一直是我們很關注的意議題之一.
PIXNET於賽前準備及提供參賽隊伍文章資料包，作為Training Data，用以讓參賽隊伍從中學習及找尋出文章與分類之間的關聯性
並準備另一包Testing Data，用以讓參賽隊伍藉由從Training Data得到的分類規則來推算，並從參賽者上傳的資料中來判定其推算的準確度


## Data Set
---
### Training Data Set
* 資料說明: 參賽者可以利用此資料集來設計推薦模型，透過 4 個月份歷史資料來預測接下來使用者有可能會看哪些文章，
* Date : 2015/03 ~ 2015/06
* [Schema Description](training_data_schema.md)
* [Download Link](http://www.pixnet.net)

### Testing Data Set
* 資料說明: 待預測的 Cookie 列表 ，參賽者必須根據這些 cookie ，產生相對應推薦文章(URL)列表
* Date : 2015/07 ~ 2015/08
* [Schema Description](testing_data_schema.md)
* [Download Link (比賽當天提供)](http://www.pixnet.net)

### Get and Analysis Data Set @AWS Redshfit
* 取得方式
* [Connection Tool Download]
* [Related Library]

### 備註:
* 由於本站資料非常龐大，故抽樣部份資抖

## 評分方式
----
### 演算法推薦結果(80%)
* 採用 Top-N Recommendation Precision and Recall 作為指標，故採用 F1 Socre　來作為最終的 Score 指標
* 定義如下：
	* P : 根據過去歷史資料(Training Data Set)，針對每一個 Cookie 推薦 Top-N 篇文章集合及為P，N 的大小會根據不同的使用者(Cookie) 而不同
	* R : 在測試資料集中(Testing Data Set) ，每一個Cookie 所瀏覽的文章集合及為 R 

	* Precsion 定義 : <img src='https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cleft%20%7C%20P%5Ccap%20R%20%5Cright%20%7C%7D%7B%5Cleft%20%7C%20P%20%5Cright%20%7C%7D'>

	* Recall 定義 :<img src='https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cleft%20%7C%20P%5Ccap%20R%20%5Cright%20%7C%7D%7B%5Cleft%20%7C%20R%20%5Cright%20%7C%7D'>


	* F1 Score 定義 :<img src='https://latex.codecogs.com/gif.latex?F_1%20%3D%202%20%5Ccdot%20%5Cfrac%7B%5Cmathrm%7Bprecision%7D%20%5Ccdot%20%5Cmathrm%7Brecall%7D%7D%7B%5Cmathrm%7Bprecision%7D%20&plus;%20%5Cmathrm%7Brecall%7D%7D'>

* 上傳預測結果取得 F1 Score
	* [上傳格式範例檔](https://github.com/pixnet/pix-recommendation/blob/master/data/result.json)
	* [上傳網址](http://www.pixnet.net)

### 簡報分數(20%)
* 簡報內容
* 演算法設計
* 資料解釋及分析




----
### 相關參考資料
* book
* paper
### 小工具
* [方程式 Gif 產生器](https://www.codecogs.com/latex/eqneditor.php)
	* smaple code :`\frac{\left | P\cap R \right |}{\left | P  \right |}`
    * sample code : `F_1 = 2 \cdot \frac{\mathrm{precision} \cdot \mathrm{recall}}{\mathrm{precision} + \mathrm{recall}}`







