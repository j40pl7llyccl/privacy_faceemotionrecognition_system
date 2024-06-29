<h1 align="center">Privacy-Conscious Analysis of Negative Facial Expressions:✨</h1>

## 研究の目的と背景: by liu hsin kuo
本研究的主要目的是开发一种在保护个人隐私的同时，能够准确识别负面表情的面部识别系统。
在现代社会中，面部识别技术广泛应用于监控摄像头和广告等领域，尤其是负面表情的准确识别在安全管理和福利领域有着重要的应用前景。
然而，面部识别与个人隐私密切相关，因此，保护个人隐私也是一个重要的课题

## 技術方法： 
在本研究中，为了在不区分面部图像中的个人识别信息的情况下识别情绪，我们采用了以下技术方法。
* **深層学習モデル**：我们结合了卷积神经网络（CNN）和残差网络（ResNet）的架构，通过深度学习提取面部表情的特征。
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/b9483151-fb36-4fd5-ba91-5d1143ab0815" alt="CNN Model" width="500" height="300">
  <br>Fig1：CNN Model
</p>
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/21d86e71-9e3d-4dfc-845f-7c789861140c" alt="CNN Model" width="500" height="500">
  <br>Fig2:Combine Model Flow Chart
</p>



* **差分プライバシー**：在模型的训练过程中，我们采用了差分隐私技术，限制训练数据集中各个数据点对模型输出的影响。
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/ddd080b3-5cbe-485b-9d75-54aa510d6866" alt="Differential privacy" width="500" height="300">
  <br>Fig3：Differential Privacy
</p>

* **データ拡張**：为了提高训练的鲁棒性，我们应用了随机变换，以增加数据集的多样性。
  
## 実験設計と方法論： 
* 数据集：使用了多个包含各种面部表情和光照条件的公开面部表情数据集。
* 预处理：使用面部检测算法提取面部区域，使模型能够专注于学习所需的特征。
* 模型训练：进行了两个阶段的训练过程。在初始阶段学习基本特征，随后应用差分隐私对模型进行微调。
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/71481316-5a89-48e5-97a8-f5f38b5a825f" alt="experimental procedures" width="500" height="300">
  <br>Fig4：Experimental Procedures
</p>

## 結果と評価： 
* 精度：相比基准模型，所提出的模型显著提高了面部表情识别的准确性。
* 隐私保护：通过实施差分隐私，个人信息泄露的风险大幅降低。
* 实用性：在复杂的现实世界场景中，模型表现出了较高的泛化能力。


## Fer2013 dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| 原始方法   | 49.219%    | 51.163%     |12.529%|6.241%|
|新しい手法|87.023%|83.321%|1.138%|1.517%|

Test Loss: 0.5789, Test Accuracy: 80.42%

1.模型性能的大幅提升

2.优秀的测试性能：

测试损失。表明模型对未见数据具有强大的泛化能力。

<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/8ca198fe-a2da-490f-9d76-b4cc190f27c7" alt="CNN Model" width="500" height="500">
  <br>Fig5:Fer2013 Confusion Matrix
</p>

这表明该模型在识别愤怒和悲伤的表情方面非常有效。

对轻蔑和厌恶类别的识别性能相对较弱，特别是轻蔑的召回率仅为18.37%。这可能是由于数据集中这些类别的样本较少所致。






## Affectnet dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| 原始方法   | 21.957%   | 23.182%     |8.702%|5.605%|
|新しい手法|70.946%|57.905%|2.372%|3.658%|

Test Loss: 1.1879, Test Accuracy: 56.77%

1.提案方法带来的显著改进

2.测试性能：
测试损失为1.1879，较高，测试精度为56.77%。尽管精度有显著提高，但较高的测试损失可能表明存在过拟合或对新数据的泛化能力问题。

<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/a7fd8412-7e7f-4f6a-91aa-af089108041e" alt="CNN Model" width="500" height="500">
  <br>Fig6:Affectnet Confusion Matrix
</p>

这表明可能需要增强模型对未见数据的泛化能力。



## Expw dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| 原始方法   | 54.679%   | 55.547%     |10.232%|6.476%|
|新しい手法|69.283%|66.796%|2.379%|2.771%|

Test Loss: 0.8813, Test Accuracy: 65.85%

1.模型性能的提升

2.测试性能分析：

测试损失为0.8813，测试精度为65.85%。虽然测试精度有所提高，但与训练和验证精度相比，仍有提升空间，这表明可能需要增强模型对未见数据的泛化能力。


<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/733d6c9a-3429-4ab2-831e-6eca8de462b5" alt="CNN Model" width="500" height="500">
  <br>Fig7:Expw Confusion Matrix
</p>

模型的性能因不同的情感类别而异。例如，它在识别悲伤表情方面表现出显著效果。
相对而言，厌恶和恐惧的识别性能较弱，特别是厌恶的召回率仅为14.84%。这可能与数据集内样本分布不均或模型对这些表情的学习不足有关。




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

