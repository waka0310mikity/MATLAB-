# 課題４レポート
画素の濃度ヒストグラムを生成せよ

## プログラム
[kadai4.m](https://github.com/waka0310mikity/MATLAB-/blob/master/kadai4.m)  
標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。

`ORG = imread('flower.JPG');`  
`ORG = rgb2gray(ORG);`  
`imagesc(ORG); colormap('gray'); colorbar;`

によって、読み込んだ画像をグレースケールし表示した結果を図1に示す。また、これを原画像とする。  

![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai4IMG1.PNG "原画像の表示")  
図１　原画像の表示

`imhist(ORG);`  

によってヒストグラフを作成、表示する。  
表示されたヒストグラフを図２に示す。  

![ヒストグラフ](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai4IMG2.PNG "ヒストグラフ")  
図2　ヒストグラフ


## 考察
`imhist(ORG);`  
はイメージ データのヒストグラムを生成する関数である。  
ヒストグラムからこの原画像の輝度値はおおよそ90から140の値が多いことがわかる。
