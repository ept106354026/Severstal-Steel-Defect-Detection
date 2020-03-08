# Severstal-Steel-Defect-Detection
Kaggle Severstal: Steel Defect Detection

- model_1022_1.ipynb 模型結果提交 
- segment_model_1024.ipynb 圖像分割模型訓練


### 簡單介紹:
找出鋼鐵圖片中缺陷的部位並且標記起來。  



### 學到的的內容:
- 了解圖像分割神經網路的架構: U-Net(雖然我是用 FPN，但我只有讀 U-Net的論文)
- TTA增強: 訓練好的模型在測試階段可以藉由將圖片做一些增強(旋轉、平移、光影變化等)產生不同的輸出，最後混合起來得到更好的結果。
- 學會使用預訓練圖像分割模型
- 了解圖像分割流程

### 流程: 

基本上需要兩個模型
1. 分類模型: 判斷圖像是否有缺陷
2. 分割模型: 標記圖像中缺陷的部位
先分類是否有缺陷在進行分割得到結果。

先分類有兩個好處:
1. 增加判斷速度，分類模型的判斷速度遠遠快於分割模型，且本次比賽有缺陷跟沒缺陷的比例約 13:87，因此先分類可以提高效率。
2. 增加分數: 判斷標準為 Dice coefficient(f1 score)，當該圖片完全沒有缺陷卻在分割模型中被判斷有缺陷，會導致該樣本的 f1 score 為0(反之為 1，滿分)，即便只有一個像素被判斷為缺陷也是，考慮這層的狀況下，多了一個分類模型可以降低這種非1即0的風險。

### 心得: 
這次因為參加的時候只剩下一周了，沒有足夠的時間研究提高分數的技巧跟嘗試足夠多的模型來做後期的合併，但至少了解到圖像分割的基本流程、跟常見的模型，也算是學到不少。
