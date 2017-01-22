# 課題8レポート
二値化された画像の連結成分にラベルをつけよ

## プログラム
[kadai8.m](https://github.com/waka0310mikity/MATLAB-/blob/master/kadai8.m)  

標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。

`ORG = imread('flower.JPG');`  
`ORG = rgb2gray(ORG);`  
`imagesc(ORG); colormap('gray'); colorbar;`

によって、読み込んだ画像をグレースケールし表示した結果を図1に示す。また、これを原画像とする。  

![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai8IMG1.PNG "原画像の表示")  
図1　原画像の表示

`IMG = ORG > 128;`

閾値128で画像を2値化する。

![2値化した画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai8IMG2.PNG "2値化した画像")  
図2　2値化した画像

`IMG = bwlabeln(IMG);`

2値化した画像をラベル付けする。

![ラベル付けした画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai8IMG3.PNG "ラベル付けした画像")  
図3　ラベル付けした画像

## 考察
`IMG = bwlabeln(IMG);`

bwlabelnは2次元バイナリイメージ内の連結要素をラベル付けする関数である。  
従って、IMGには検出された8連結オブジェクトのラベルを含むラベル行列が返され、ラベル付けされた画像を生成することができる。
