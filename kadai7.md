# 課題7レポート  
画素のダイナミックレンジを０から２５５にせよ．  

## プログラム
[kadai7.m](https://github.com/waka0310mikity/MATLAB-/blob/master/kadai7.m)

標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。

`ORG = imread('flower.JPG');`  
`ORG = rgb2gray(ORG);`  
`imagesc(ORG); colormap('gray'); colorbar;`

によって、読み込んだ画像をグレースケールし表示した結果を図1に示す。また、これを原画像とする。

![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai7IMG1.PNG "原画像の表示")  
図1　原画像の表示

`imhist(ORG);`

によって濃度ヒストグラムを生成、表示する。

![ヒストグラム](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai7IMG2.PNG "ヒストグラム")  
図2　ヒストグラム

`ORG = double(ORG);`  
`mn = min(ORG(:));`  
`mx = max(ORG(:));`  
`ORG = (ORG-mn)/(mx-mn)*255;`  
`imagesc(ORG); colormap(gray); colorbar;`  

![処理後の画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai7IMG3.PNG "処理後の画像")  
図3　処理後の画像  

![処理後のヒストグラム](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai7IMG4.PNG "処理後のヒストグラム")  
図4　処理後のヒストグラム

## 考察

`ORG = uint8(ORG);`

unit8とは8ビット符号なし整数へ変換する関数である。  
従って、上記のプログラムは変数ORGにORGを8ビット符号なし整数に変換した値を代入している。  
