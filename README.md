# Severstal-Steel-Defect-Detection
Kaggle Severstal: Steel Defect Detection

- model_1022_1.ipynb 模型結果提交 
- segment_model_1024.ipynb 圖像分割模型訓練


簡單介紹:
找出鋼鐵圖片中缺陷的部位並且標記起來。  



學到的的內容:
- 了解圖像分割神經網路的架構: U-Net(雖然我是用 FPN，但我只有讀 U-Net的論文)
- TTA增強: 訓練好的模型在測試階段可以藉由將圖片做一些增強(旋轉、平移、光影變化等)產生不同的輸出，最後混合起來得到更好的結果。
- 學會使用預訓練圖像分割模型
- 了解圖像分割流程

流程: 
評分標準為 Dice coefficient，物理意義為下:

X: 預測的缺陷部位
Y: 真實的缺陷部位
<img src="http://chart.googleapis.com/chart?cht=tx&chl= \cfrac {2*|X\cap Y|}{|X|+|Y|}" style="border:none;">
Dice coefficient = 



基本上需要兩個模型
1. 分類模型: 判斷圖像是否有缺陷
2. 分割模型: 標記圖像中缺陷的部位



心得: 了解到圖像分割的基本流程、跟常見的模型。
