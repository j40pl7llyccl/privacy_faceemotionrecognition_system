<h1 align="center">Privacy-Conscious Analysis of Negative Facial Expressions:✨</h1>

## 研究の目的と背景: by liu hsin kuo
本研究的主要目的是開發一種在保護個人隱私的同時，能夠準確識別負面表情的面部識別系統。
在現代社會中，面部識別技術廣泛應用於監控攝像頭和廣告等領域，尤其是負面表情的準確識別在安全管理和福利領域具有重要的應用前景。
然而，面部識別與個人隱私密切相關，因此，保護個人隱私也是一個重要的課題。

## 技術方法： 
在本研究中，為了在不區分臉部影像中的個人識別資訊的情況下識別情緒，我們採用了以下技術方法。
* **深層学習モデル**：我們結合了卷積神經網路（CNN）和殘差網路（ResNet）的架構，透過深度學習提取臉部表情的特徵。
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/b9483151-fb36-4fd5-ba91-5d1143ab0815" alt="CNN Model" width="500" height="300">
  <br>Fig1：CNN Model
</p>
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/21d86e71-9e3d-4dfc-845f-7c789861140c" alt="CNN Model" width="500" height="500">
  <br>Fig2:Combine Model Flow Chart
</p>



* **差分プライバシー**：在模型的訓練過程中，我們採用了差分隱私技術，限制訓練資料集中各個資料點對模型輸出的影響。
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/ddd080b3-5cbe-485b-9d75-54aa510d6866" alt="Differential privacy" width="500" height="300">
  <br>Fig3：Differential Privacy
</p>

* **データ拡張**：為了提高訓練的穩健性，我們應用了隨機變換，以增加資料集的多樣性。
  
## 実験設計と方法論： 
* 資料集：使用了多個包含各種臉部表情和光線條件的公開臉部表情資料集。
* 預處理：使用臉部偵測演算法提取臉部區域，使模型能夠專注於學習所需的特徵。
* 模型訓練：進行了兩個階段的訓練過程。在初始階段學習基本特徵，隨後應用差分隱私對模型進行微調。
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/71481316-5a89-48e5-97a8-f5f38b5a825f" alt="experimental procedures" width="500" height="300">
  <br>Fig4：Experimental Procedures
</p>

## 結果と評価： 
* 精度：相比基準模型，所提出的模型顯著提高了面部表情識別的準確性。
* 隱私保護：通過實施差分隱私，個人資訊洩露的風險大幅降低。
* 實用性：在複雜的現實世界場景中，模型表現出了較高的泛化能力。


## Fer2013 dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| 原始方法   | 49.219%    | 51.163%     |12.529%|6.241%|
|新しい手法|87.023%|83.321%|1.138%|1.517%|

Test Loss: 0.5789, Test Accuracy: 80.42%

1.模型性能的大幅提升

2.優秀的測試性能：

測試損失。顯示模型對未見資料具有強大的泛化能力。

<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/8ca198fe-a2da-490f-9d76-b4cc190f27c7" alt="CNN Model" width="500" height="500">
  <br>Fig5:Fer2013 Confusion Matrix
</p>

這表明該模型在識別憤怒和悲傷的表情方面非常有效。

對輕蔑和厭惡類別的辨識表現相對較弱，特別是輕蔑的回想率僅為18.37%。這可能是由於資料集中這些類別的樣本較少所致。






## Affectnet dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| 原始方法   | 21.957%   | 23.182%     |8.702%|5.605%|
|新しい手法|70.946%|57.905%|2.372%|3.658%|

Test Loss: 1.1879, Test Accuracy: 56.77%

1.提案方法帶來的顯著改進

2.測試性能：
測試損失為 1.1879，較高；測試精度為 56.77%。儘管精度有顯著提高，但較高的測試損失可能表明存在過擬合或對新數據的泛化能力問題。

<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/a7fd8412-7e7f-4f6a-91aa-af089108041e" alt="CNN Model" width="500" height="500">
  <br>Fig6:Affectnet Confusion Matrix
</p>

這表明可能需要增強模型對未見資料的泛化能力。



## Expw dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| 原始方法   | 54.679%   | 55.547%     |10.232%|6.476%|
|新しい手法|69.283%|66.796%|2.379%|2.771%|

Test Loss: 0.8813, Test Accuracy: 65.85%

1.模型性能的提升

2.測試性能分析：

測試損失為0.8813，測試精度為65.85%。雖然測試精度有所提高，但與訓練和驗證精度相比，仍有提升空間，這表明可能需要增強模型對未見資料的泛化能力。


<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/733d6c9a-3429-4ab2-831e-6eca8de462b5" alt="CNN Model" width="500" height="500">
  <br>Fig7:Expw Confusion Matrix
</p>

模型的性能因不同的情感類別而異。例如，它在識別悲傷表情方面表現出顯著效果。
相對而言，厭惡和恐懼的識別性能較弱，特別是厭惡的召回率僅為 14.84%。這可能與數據集中樣本分布不均或模型對這些表情的學習不足有關。




## Citation

```
@misc{privacy_faceemotionrecognition_system,
      title={privacy_faceemotionrecognition_system: A system that can detect the negative of face emotion recognition},
      author={Liu Hsin Kuo},
      year={2023},
}
```

参考論文：
1. [1]Shervin Minaee1 , Amirali Abdolrashidi2 1Expedia Group 2University of California, Riverside”Deep-Emotion: Facial Expression Recognition Using Attentional  Convolutional Network”2019.
1. [2]Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun”Deep Residual Learning for Image Recognition”10 Dec 2015.
1. [3]Connor Shorten & Taghi M. Khoshgoftaar”A survey on Image Data Augmentation for Deep Learning”Springer Link 2019.
1. [4]C. Dwork. Differential privacy. M. Bugliesi, B. Preneel, V. Sassone, and I. Wegener, (eds) Automata, Languages and Programming, 4052, 2006.
1. [5]Zhang, Yulun, et al. "Deep fusion network for image completion." Proceedings of the European Conference on Computer Vision (ECCV). 2018.
1. [6]Opitz, Michael, Horst Bischof, and Georg Waltner. "Diverse Multi-model Fusion." Proceedings of the IEEE International Conference on Computer Vision Workshops. 2015.
1. [7]Yang Xu, Zhixiong Li, Shuqing Wang, Weihua Li, T. Sarkodie-Gyan, Shizhe Feng”A hybrid deep-learning model for fault diagnosis of rolling bearings”7 Mar 2022.
1. [8]Ashkan Yousefpour, Igor Shilov, Alexandre Sablayrolles, Davide Testuggine, Karthik Prasad, Mani Malek, John Nguyen, Sayan Ghosh, Akash Bharadwaj, Jessica Zhao, Graham Cormode, Ilya Mironov”Opacus: User-Friendly Differential Privacy Library in PyTorch”25 Sep 2021.
1. [9]Ilya Loshchilov, Frank Hutter”Decoupled Weight Decay Regularization”14 Nov 2017.
1. [10]Insight Centre for Data Analytics, NUI Galway Aylien Ltd.,Dublin. "An overview of gradient descent optimization algorithms"  2017.

