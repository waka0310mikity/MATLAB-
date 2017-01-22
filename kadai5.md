# 課題５レポート  
判別分析法を用いて画像二値化せよ。

## プログラム
[kadai5.m](https://github.com/waka0310mikity/MATLAB-/blob/master/kadai5.m)  
標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。  

`ORG = imread('flower.JPG');`  
`ORG = rgb2gray(ORG);`  
`imagesc(ORG); colormap('gray'); colorbar;`

によって、読み込んだ画像をグレースケールし表示した結果を図1に示す。また、これを原画像とする。  

![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai5IMG1.PNG "原画像の表示")  
図1　原画像の表示

`IMG = ORG > max_thres;`  
`imagesc(ORG); colormap('gray'); colorbar;`  
判別分析法にて二値化した画像を表示。

![二値画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai5IMG2.PNG "二値画像の表示")  
図2　二値画像の表示

## 考察
判別分析法とは、対象物の濃度と、背景の濃度とがそれぞれ最もよくまとまり、かつ対象物と背景との違いが際立つように閾値を定める方法である。  
max_thresは閾値、myu1はC1の、myu2はC2の平均値、sigma1はC1、sigma2はC2のクラス内分散を表す。
