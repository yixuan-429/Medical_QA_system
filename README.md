一問醫答 AI in Medical QA System
==
本專案旨在構建第一個中文醫療QA系統聊天機器人。透過蒐集繁體中文的相關衛教網站作為資料庫，通過聊天機器人，用戶可以輸入他們對症狀的主訴，機器人會推薦相關的看診科別與推薦參考的文章。
## web crawling 
本專案蒐集了來自7個台灣衛教網站的衛教文章作為我們資料庫，透過透過觀察每個衛教網站的原始碼，將衛教文章的網站與名稱給蒐集起來。
7個衛教網站分別來自UDN元氣網、康健知識庫、奇美衛教資訊網、kenkon健康網、仁愛醫療材團法人全球資訊網、今健康、中亞健康網，最後收集了4861篇文章。

## Data pre-processing
在4861篇文章，我們使用 CkipTagger 進行繁體中文的斷詞，再使用
stop word list 除去停用詞，如你、我、他以及標點符號等。最後再以 Word2Vec 去計算字詞之間的相似性。

## Unsupervised
透過使用 Embedding的方式，去計算各文章經過處理後的文字所對應的向量，經過 Cosine Similarity，去計算最適合的衛教文章。

## Supervised
透過對112條自然語言敘述的主訴，去標籤其對應的科別。接著使用LSTM的模型進行訓練，當使用者輸入主訴後，可以計算相關的看診科別。

## API 
將後端的資料處理、LSTM的模型、推薦相關的看診科別與參考文章的code整理成class的模式，掛到API上，使其可以跟chat bot做結合，整理成前端的模式。

## Visualize
- 使用PCA降低embedding的維度，並且使用2D的PCA已呈現文字間的相關性。
- 使用confusion matrix去看多分類型的預測結果，Y軸是我們標籤的科別，X軸是我們預測的科別。



- 👋 Hi, I’m @sc201groupc
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
sc201groupc/sc201groupc is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->


