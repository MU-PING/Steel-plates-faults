# Steel-plates-faults
## 程式簡介
### 簡述
* 使用「類神經網路」實作 [Kaggle](https://www.kaggle.com/) - [Steel Plates Faults](https://www.kaggle.com/datasets/uciml/faulty-steel-plates/code) 資料集，目的是「鋼板故障種類」之分類

* csv檔前27欄是訓練資料的特徵( 沒有詳細說明 )；最後7欄表示錯誤類型，代表Label

* 同時實作以下兩種資料科學相關的技術：
    * N - Cross fold validation ( 交叉驗證 )
    
    * Confusion matrix ( 混淆矩陣 )

> 類神經網路 與 資料前處理 在其他文章介紹過，此篇不會詳細介紹，可直接觀看程式碼

### 範例圖
* **Partial Dataset ( After standardization )**

![](https://i.imgur.com/iGW5kF5.png)

* **N - Cross fold validation**

![](https://i.imgur.com/tpHJZ6g.png)

* **Confusion matrix**

![](https://i.imgur.com/zay1T9W.png)

* **Neural Network output**

![](https://i.imgur.com/bD9XI6q.png)
![](https://i.imgur.com/FFYSXYE.png)
## 交叉驗證、混淆矩陣 簡單介紹

### N - Cross fold validation ( 交叉驗證 )
> 亦稱循環估計
* 步驟如下：
    1. 先將資料集分割成 N 個子集，選擇其中一個子集做「測試集」，而其它子集做「訓練集」
    2. 依照「訓練集」訓練模型，並根據「測試集」得到一個評估結果( ACC、MAS等... )
    3. 循環 1、2 步驟，將每個子集都當作過「測試集」一次，這樣可以得到 N 個評估結果
    4. 最後平均所有評估結果，作為模型最終的性能評估標準。

* 同時「訓練集」在訓練時，可再區分出一部分「驗證集」幫助模型調整參數
* N - Cross fold validation的示意圖如下：

![](https://i.imgur.com/Pma5gG3.png)

* 交叉驗證的主要目的**是用來「測試模型的性能」，減少諸如過擬合和選擇偏差等問題**
### Confusion matrix ( 混淆矩陣 )
> 亦稱誤差矩陣，一種資料視覺化技術
* 用於「分類的監督式學習」或「聚類的非監督式學習」，在非監督式學習中一般稱為匹配矩陣。

* 將「預測類別」與「真實類別」的關係做成矩陣形式，列代表「預測類別」；行表示「真實類別」( 相反也可以 )，特徵與示意圖如下:
    * 矩陣大小會是**類別數量的平方**
    
    * 綠色區塊代表**分類正確**；紅色區塊代表**分類錯誤**
      
    ![](https://i.imgur.com/WuekO2a.png)

* 混淆矩陣可方便、快速地看出模型是否將兩個不同的類別混淆了( 把一個類錯誤判成了另一個類 ）。
