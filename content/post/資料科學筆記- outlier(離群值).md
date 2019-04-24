+++
title = "資料科學筆記-template"

# View.
#   1 = List
#   2 = Compact
#   3 = Card
view = 3
+++

## 筆記統整
  * 最近參加資料百日挑戰賽，在第六天提到的離群值，提供兩篇參考資料：
  １. [Ways to Detect and Remove the Outliers](https://towardsdatascience.com/ways-to-detect-and-remove-the-outliers-404d16608dba)  
  ２. [How to Use Statistics to Identify Outliers in Data](https://machinelearningmastery.com/how-to-use-statistics-to-identify-outliers-in-data/)  
###  "Ｗays to detect" 文章當中提到幾種檢驗outliers的方式：
  * Uni-variate outlier or multivariate outlier analysis   
  * Z-score - relationship with the Standard Deviation and Mean of the group of data points. Outliers  =  abs(zscore) > 3  
  visualise outliers by using: 1. box plot 2. scatter plot  
  * IQR = Q3 - Q1 。 Outliers < Q1 - 1.5 * IQR | Outliers > Q3 + 1.5 * IQR
### "How to use" 文章
  * 簡要的提一下outliers的可能成因：
  1. 手誤或量測錯誤
  2. 資料毀損
  3. 特別突出
  第一二點個人認為只能想辦法刪補值，第三點比較有趣，作者提到喬丹在籃球員中特別突出，也算是個離群值的例子。  
  你不能因為他表現太好而認為他數據有問題，進行刪補替換資料等動作。
  * 除了上一篇提到的分位數的做法，此篇用到統計上找離群值常見的方式: Mean +/-  (2 or 3 Std)
  
### 經驗連結
  * 過往經驗的分享
### 程式實作
  * 實作程式碼
  
