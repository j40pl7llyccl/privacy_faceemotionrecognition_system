## 研究の目的と背景: by liu hsin kuo
本研究の主要な目的は、個人のプライバシーを保護しながら、ネガティブな表情を正確 
に識別する顔認識システムの開発です。現代社会において、監視カメラや広告などの分 
野で顔認識技術が広く応用されており、特にネガティブな表情の正確な認識は、安全管 
理や福祉の分野での応用が期待されます。しかしながら、顔認識は個人のプライバシー 
と密接に関わるため、その保護も重要な課題となっています。 

## 技術方法： 
本研究では、顔画像の中の個人識別情報を区別することなく感情を識別するために、以下の技術的方法を採用しました。 
* **深層学習モデル**：畳み込みニューラルネットワーク（CNN）と残差ネットワーク （ResNet）のアーキテクチャを組み合わせ、深層学習を通じて顔表情の特徴を抽出します。 
* **差分プライバシー**：モデルのトレーニングプロセスにおいて、差分プライバシーを 採用し、トレーニングデータセット内の個別データポイントがモデルの出力に与え る影響を限定します。 
* **データ拡張**：トレーニングの堅牢性を高めるために、ランダムな変換を適用しデータセットの多様性を増加させます。
  
## 実験設計と方法論： 
* データセット：さまざまな顔表情と照明条件のデータを含む複数の公開顔表情データセットを使用しました。 
* プリプロセッシング：顔検出アルゴリズムを使用して顔領域を抽出し、モデルが学習に必要な特徴に集中できるようにしました。 
* モデルトレーニング：2 段階のトレーニングプロセスを実施。初期段階では基本特徴の学習を行い、続いて差分プライバシーを適用してモデルを微調整しました。結果と評価： 
* 精度：提案されたモデルは、基準モデルと比較して、顔表情認識の精度を顕著に向上させました。 
* プライバシー保護：差分プライバシーの実施により、個人を特定する情報の漏えいリスクが大幅に減少しました。 
* 実用性：複雑な現実世界のシナリオでも、モデルは高い一般化能力を示しました。 


## Fer2013 dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| オリジナル   | 49.219%    | 51.163%     |12.529%|6.241%|
|新しい手法|87.023%|83.321%|1.138%|1.517%|



## Affectnet dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| オリジナル   | 21.957%   | 23.182%     |8.702%|5.605%|
|新しい手法|70.946%|57.905%|2.372%|3.658%|



## Expw dataset

|  | Train Accuracy | Validation Accuracy|Tain Loss|Validation Loss|
| -------- | -------- | -------- |-----|-----|
| オリジナル   | 54.679%   | 55.547%     |10.232%|6.476%|
|新しい手法|69.283%|66.796%|2.379%|2.771%|


今後の展望： 
データセットの拡充：より多様な背景と表情を含むデータセットに対するモデルの適応性を検証します。

参考論文：
1. [1]Shervin Minaee1 , Amirali Abdolrashidi2 1Expedia Group 2University of California, Riverside”Deep-Emotion: Facial Expression Recognition Using Attentional  Convolutional Network”2019.
1. [2]Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun”Deep Residual Learning for Image Recognition”10 Dec 2015
1. [3]Connor Shorten & Taghi M. Khoshgoftaar”A survey on Image Data Augmentation for 
1. Deep Learning”Springer Link 2019
1. [4]C. Dwork. Differential privacy. M. Bugliesi, B. Preneel, V. Sassone, and I. Wegener, (eds) Automata, Languages and Programming, 4052, 2006.
1. [5]Zhang, Yulun, et al. "Deep fusion network for image completion." Proceedings of the European Conference on Computer Vision (ECCV). 2018.
1. [6]Opitz, Michael, Horst Bischof, and Georg Waltner. "Diverse Multi-model Fusion." Proceedings of the IEEE International Conference on Computer Vision Workshops. 2015.
1. [7]Yang Xu, Zhixiong Li, Shuqing Wang, Weihua Li, T. Sarkodie-Gyan, Shizhe Feng”A hybrid deep-learning model for fault diagnosis of rolling bearings”7 Mar 2022.
1. [8]Ashkan Yousefpour, Igor Shilov, Alexandre Sablayrolles, Davide Testuggine, Karthik Prasad, Mani Malek, John Nguyen, Sayan Ghosh, Akash Bharadwaj, Jessica Zhao, Graham Cormode, Ilya Mironov”Opacus: User-Friendly Differential Privacy Library in PyTorch”25 Sep 2021.
1. [9]Ilya Loshchilov, Frank Hutter”Decoupled Weight Decay Regularization”14 Nov 2017.
1. [10]Insight Centre for Data Analytics, NUI Galway Aylien Ltd.,Dublin. "An overview of gradient descent optimization algorithms"  2017.

