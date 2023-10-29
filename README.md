# Google-Colab
完全雲端運行：使用Google-CoLaboratory訓練神經網路
Colaboratory 是一個Google 研究項目，旨在幫助傳播機器學習培訓和研究成果。它是一個Jupyter 筆記本環境，不需要進行任何設定就可以使用，並且完全在雲端運行。Colaboratory 筆記本儲存在Google 雲端硬碟(https://drive.google.com/) 中，並且可以分享，就如同您使用Google 文件或表格一樣。Colaboratory 可免費使用。本文介紹如何使用Google CoLaboratory 訓練神經網路。
工具連結：https://colab.research.google.com/

谷歌近期上線了協作寫程式碼的內部工具Google CoLaboratory。Colaboratory 是一個Google 研究項目，旨在幫助傳播機器學習培訓和研究成果。它是一個Jupyter 筆記本環境，不需要進行任何設定就可以使用，並且完全在雲端運行。

Colaboratory 筆記本儲存在Google 雲端硬碟(https://drive.google.com/) 中，並且可以分享，就如同您使用Google 文件或表格一樣。Colaboratory 可免費使用。

CoLaboratory
首先，請造訪CoLaboratory 網站（http://g.co/colab），註冊後接受使用該工具的邀請。確認郵件通常需要一天才能回到你的郵箱。CoLaboratory 允許使用Google虛擬機器執行機器學習任務和建立模型，無需擔心計算力的問題，而且它是免費的。

開啟CoLaboratory，會出現一個「Hello, Colaboratory」文件，包含一些基本範例。建議嘗試一下。

使用CoLaboratory 可以在Jupyter Notebook 上寫程式碼。寫好後執行(Shift + Enter)，程式碼單元下方就會產生輸出。
![image](https://github.com/ytgh09050/Google-Colab/assets/111853085/97050690-df11-4a79-b6b7-bd4ea27e83c1)
除了寫程式碼，CoLaboratory 還有一些技巧（trick）。你可以在notebook 中shell 指令前加上「!」。如：!pip install -q keras。這樣你就可以很大程度上控制正在使用的Google虛擬機器。點擊左上方（選單列下）的黑色按鈕就可以找到它們的程式碼片段。

本文旨在展示如何使用CoLaboratory 訓練神經網路。我們將展示一個在威斯康辛乳癌資料集上訓練神經網路的範例，資料集可在UCI Machine Learning Repository（http://archive.ics.uci.edu/ml/datasets）取得。本文的範例相對比較簡單。

本文所使用的CoLaboratory notebook 連結：https://colab.research.google.com/notebook#fileId=1aQGl_sH4TVehK8PDBRspwI4pD16xIR0r

深度學習
深度學習是一種機器學習技術，它所使用的計算技術一定程度上模仿了生物神經元的運作。各層中的神經元網路不斷將資訊從輸入傳輸到輸出，直到其權重調整到可以產生反映特徵和目標之間底層關係的演算法。

想更了解神經網絡，推薦閱讀這篇論文《Artificial Neural Networks for Beginners》（https://arxiv.org/pdf/cs/0308031.pdf）。

Keras
是一種建構人工神經網路的高階API。它使用TensorFlow 或Theano 後端執行內部運作。要安裝Keras，必須先安裝TensorFlow。CoLaboratory 已經在虛擬機器上安裝了TensorFlow。使用以下指令可以檢查是否安裝TensorFlow：

!pip show tensorflow

你也可以使用!pip install tensorflow==1.2，安裝特定版本的TensorFlow。

另外，如果你更喜歡用Theano 後端，可以閱讀該文件：https://keras.io/backend/。

混淆矩陣

混淆矩陣是模型做出的正確、錯誤預測的矩陣表徵。此矩陣可供個人調查哪些預測和另一種預測混淆。這是一個2×2 的混淆矩陣。
![image](https://github.com/ytgh09050/Google-Colab/assets/111853085/a0412fc7-53c2-40bb-84d5-94253a76c207)

