+++
title = "資料科學筆記-handle missing values(遺漏值)"

# View.
#   1 = List
#   2 = Compact
#   3 = Card
view = 3
+++

### 筆記統整
  * 參考了幾篇關於遺漏值的文章:
  1. [Missing Values in Data](https://www.statisticssolutions.com/missing-values-in-data/)
  2. [How to Handle Missing Data](https://towardsdatascience.com/how-to-handle-missing-data-8646b18db0d4)  
  
  遺失值又可以分成幾大項:  
  * MCAR: Missing completely at random. 遺失的值與其他欄位(columns)資料無關。
  
  * MAR:  Missing at random. 遺失資料與其他欄位資料有一定相關性。 如年紀大的人可能填表格時比較容易漏填(遺失成因偏向非故意，純粹是種低發生率之間的相對高的現象)。  
  
  * MNAR: Missing not at Random. 遺失值背後代表有某種規律成因。 如**高比例**女性對於體重資料或是高收入族群填寫收入欄位時可能會避填，而造成判讀上容易有bias。  

#### 刪除
  "In statistical language, if the number of the cases is less than 5% of the sample, then the researcher can drop them."(ref. 1),統計學上有個判斷遺失值是否可以直接刪除的標準，就是遺失的比例如果小於5％就可以直接刪除。 但是如果講究一些，只有在MCAR的情況下可以直接進行刪除動作，其他遺失種類如MAR、NMAR就不適合這樣處理。How to handle的作者則建議填補資料資料為優先選項，萬不得已才刪除資料。  

#### 補值  
  補值最簡單的方式就是直接補平均值、中位數、眾數，但缺點是會影響變異數，varience則會影響模型flexibility。[Imputation of missing values - sklearn](https://scikit-learn.org/stable/modules/impute.html#impute)。    
  另外一種常見的方式是利用線性回歸的方式(前提是假設變數之間有線性關係)，利用已有的完整資料訓練回歸模型，將遺失值當作依變項來預測。，缺點是可能會資料長得太像，而影響模型robust。  
  [Multiple imputation](https://en.wikipedia.org/wiki/Imputation_(statistics))也是種常見的補值方式，方法簡述如下：先建立回歸模型並用之產生幾個normal distributions，隨機從各個distribution當中抽樣輪流補值，然後分析各個補值結果進行分析，利用多次迭代使結果趨向穩定並得到適當估計(填補)值。     

### 經驗連結
  * 刪除的方式有幾種：1. 直接刪除整個column 2. 只刪除某幾個rows
  後續研讀:
  * [A review of techniques for treating missing data in OM survey research](http://edmeasurement.net/5245/Tsikriktsis-2005.pdf)
  * [Missing Data Conundrum: Exploration and Imputation Techniques](https://medium.com/ibm-data-science-experience/missing-data-conundrum-exploration-and-imputation-techniques-9f40abe0fd87)

### 程式實作
  * [Imputing Missing Class Labels Using k-Nearest Neighbors](https://chrisalbon.com/machine_learning/preprocessing_structured_data/imputing_missing_class_labels_using_k-nearest_neighbors/)  
  * [fancyimpute-補值套件](https://github.com/iskandr/fancyimpute)
  * [missingno-遺失值視覺化套件](https://github.com/ResidentMario/missingno)
  
  
  
  
  
