# 大數據與商業分析期中專案 - 以新聞報導做股價預測
本專案目標為以新聞文章來預測股票未來的表現：  
資料集：群創（股票代號：3481）在2021年所有 bbs, forum 中新聞文章  
資料前處理：  
 1. 將群創 2021 年的股價表現整理後，得出該股在哪幾天的股價起伏超過 0.5%
 2. 將這些日期的所有新聞資料都取出，並以 keyword '群創‘, '面板', '3481' 將與群創相關的所有新聞資料取出  
----------------------------------------  
模型使用：BernoulliNB, kNN, SVM, GradientBoostingClassifier  
模型建立：  
 1. 將新聞資料利用 monpa, ckiptagger 斷詞
 2. 將斷詞好的 token 以 TFIDF 評估 token 重要性，並依重要性取出 1000 個 token
 3. 將新聞資料丟入模型訓練，並算出準確率
-----------------------------------------
預測結果：
 1. SVM Linear:  
 | precision  | precision  | recall || F1-score | support |
 | ------------- | ------------- | ------------- || ------------- | ------------- |
 | 漲  | 0.66  | 0.39  || 0.49  | 1230  |
 | 跌  | 0.25  | 0.51  || 0.33  | 490  |
 | accurancy  |   |   || 0.42  | 1720  |
 | macro avg  | 0.46  | 0.45  || 0.41  | 1720  |
 | weighted avg  | 0.55  | 0.42  || 0.44  | 1720  |  
 
