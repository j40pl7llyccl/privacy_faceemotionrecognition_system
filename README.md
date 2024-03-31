<h1 align="center">Privacy-Conscious Analysis of Negative Facial Expressions:✨</h1>

## 研究の目的と背景: by liu hsin kuo
本研究の主要な目的は、個人のプライバシーを保護しながら、ネガティブな表情を正確 
に識別する顔認識システムの開発です。現代社会において、監視カメラや広告などの分 
野で顔認識技術が広く応用されており、特にネガティブな表情の正確な認識は、安全管 
理や福祉の分野での応用が期待されます。しかしながら、顔認識は個人のプライバシー 
と密接に関わるため、その保護も重要な課題となっています。 

## 技術方法： 
本研究では、顔画像の中の個人識別情報を区別することなく感情を識別するために、以下の技術的方法を採用しました。 
* **深層学習モデル**：畳み込みニューラルネットワーク（CNN）と残差ネットワーク （ResNet）のアーキテクチャを組み合わせ、深層学習を通じて顔表情の特徴を抽出します。
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/b9483151-fb36-4fd5-ba91-5d1143ab0815" alt="CNN Model" width="500" height="300">
  <br>Fig1：CNN Model
</p>
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/21d86e71-9e3d-4dfc-845f-7c789861140c" alt="CNN Model" width="500" height="500">
  <br>Fig2:Combine Model Flow Chart
</p>



* **差分プライバシー**：モデルのトレーニングプロセスにおいて、差分プライバシーを 採用し、トレーニングデータセット内の個別データポイントがモデルの出力に与え る影響を限定します。
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/ddd080b3-5cbe-485b-9d75-54aa510d6866" alt="Differential privacy" width="500" height="300">
  <br>Fig3：Differential Privacy
</p>

* **データ拡張**：トレーニングの堅牢性を高めるために、ランダムな変換を適用しデータセットの多様性を増加させます。
  
## 実験設計と方法論： 
* データセット：さまざまな顔表情と照明条件のデータを含む複数の公開顔表情データセットを使用しました。 
* プリプロセッシング：顔検出アルゴリズムを使用して顔領域を抽出し、モデルが学習に必要な特徴に集中できるようにしました。 
* モデルトレーニング：2 段階のトレーニングプロセスを実施。初期段階では基本特徴の学習を行い、続いて差分プライバシーを適用してモデルを微調整しました。
<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/71481316-5a89-48e5-97a8-f5f38b5a825f" alt="experimental procedures" width="500" height="300">
  <br>Fig4：Experimental Procedures
</p>

## 結果と評価： 
* 精度：提案されたモデルは、基準モデルと比較して、顔表情認識の精度を顕著に向上させました。 
* プライバシー保護：差分プライバシーの実施により、個人を特定する情報の漏えいリスクが大幅に減少しました。 
* 実用性：複雑な現実世界のシナリオでも、モデルは高い一般化能力を示しました。 


## Fer2013 dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| オリジナル   | 49.219%    | 51.163%     |12.529%|6.241%|
|新しい手法|87.023%|83.321%|1.138%|1.517%|

Test Loss: 0.5789, Test Accuracy: 80.42%

1.モデルのパフォーマンスの大幅な向上:

2.優れたテストパフォーマンス:

テスト損失。目に見えないデータに対するモデルの強力な汎化能力を示します。

<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/8ca198fe-a2da-490f-9d76-b4cc190f27c7" alt="CNN Model" width="500" height="500">
  <br>Fig5:Fer2013 Confusion Matrix
</p>

これは、このモデルが怒りや悲しみの表現を認識するのに非常に効果的であることを示しています。

軽蔑と嫌悪のカテゴリの認識パフォーマンスは比較的弱く、特に軽蔑の再現率はわずか 18.37% でした。 これは、データセット内のこれらのカテゴリのサンプルが少ないことが原因である可能性があります。






## Affectnet dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| オリジナル   | 21.957%   | 23.182%     |8.702%|5.605%|
|新しい手法|70.946%|57.905%|2.372%|3.658%|

Test Loss: 1.1879, Test Accuracy: 56.77%

1.提案手法による大幅な改善:

2.テストパフォーマンス:
テスト損失は 1.1879 と比較的高く、テスト精度は 56.77% です。 精度には顕著な改善が見られますが、高いテスト損失は、過剰適合または新しいデータへの一般化に関する問題を示している可能性があります。

<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/a7fd8412-7e7f-4f6a-91aa-af089108041e" alt="CNN Model" width="500" height="500">
  <br>Fig6:Affectnet Confusion Matrix
</p>

これは、目に見えないデータに対するモデルの一般化能力を強化する必要がある可能性があることを示唆しています。



## Expw dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| オリジナル   | 54.679%   | 55.547%     |10.232%|6.476%|
|新しい手法|69.283%|66.796%|2.379%|2.771%|

Test Loss: 0.8813, Test Accuracy: 65.85%

1.モデルのパフォーマンスの向上:

2.テストパフォーマンス分析:

テスト損失は 0.8813 で、テスト精度は 65.85% でした。 テストの精度は向上していますが、トレーニングおよび検証の精度と比較するとまだ強化の余地があり、目に見えないデータに対するモデルの汎化能力を強化する必要がある可能性があることを示唆しています。


<p align="center">
  <img src="https://github.com/j40pl7llyccl/privacy_faceemotionrecognition_system/assets/24970006/733d6c9a-3429-4ab2-831e-6eca8de462b5" alt="CNN Model" width="500" height="500">
  <br>Fig7:Affectnet Confusion Matrix
</p>

モデルのパフォーマンスは、さまざまな感情カテゴリーによって異なりました。 たとえば、悲しみの表現を認識するのに顕著な効果があることを示しています。
対照的に、嫌悪感と恐怖の認識性能は弱く、特に嫌悪感の再現率はわずか 14.84% でした。 これは、データセット内のサンプル分布が不均一であること、またはモデルによるこれらの式の学習が不十分であることに関連している可能性があります。




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

