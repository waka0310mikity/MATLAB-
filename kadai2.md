# 課題２レポート
２階調，４階調，８階調の画像を生成せよ。

## プログラム
[kadai2.m](https://github.com/waka0310mikity/MATLAB-/blob/master/kadai2.m)  
標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。  

`ORG = imread('flower.JPG');`  
`ORG = rgb2gray(ORG);`  
`imagesc(ORG); colormap('gray'); colorbar;`

によって、読み込んだ画像をグレースケールし表示した結果を図1に示す。また、これを原画像とする。  

![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai2IMG1.PNG "原画像の表示")  
図１　原画像の表示

原画像を2階調にするには、しきい値を一つ定めればよい。

`IMG = ORG>128;`  
`imagesc(IMG); colormap(gray); colorbar;  axis image;`  

2階調画像を図2に示す。  

![2階調画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai2IMG2.PNG "2階調画像")  
図2　2階調画像  

次に、原画像を4階調にするにはしきい値を四つ定める。  

`IMG0 = ORG>64;`  
`IMG1 = ORG>128;`  
`IMG2 = ORG>192;`  
`IMG = IMG0 + IMG1 + IMG2;`  
`imagesc(IMG); colormap(gray); colorbar;  axis image;`  

4階調画像を図3に示す。  

![4階調画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai2IMG3.PNG "4階調画像")  
図3　4階調画像  

同様に、8階調画像を生成するにはしきい値を8つ定める。
`IMG0 = ORG>32;`  
`IMG1 = ORG>64;`  
`IMG2 = ORG>96;`  
`IMG3 = ORG>128;`  
`IMG4 = ORG>160;`  
`IMG5 = ORG>192;`  
`IMG6 = ORG>224;`  
`IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;`  
`imagesc(IMG); colormap(gray); colorbar;  axis image;`  

![8階調画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai2IMG4.PNG "8階調画像")  
図4　8階調画像

## 考察
はじめに設定した2階調画像の閾値128を基準として、その1/2を128から引いた値、足した値を閾値として加えることで4階調画像が生成されている。  
従って、8階調画像の生成には4階調画像の閾値64を基準として、その1/2を0から8つずつ足していくことで閾値を定めるとよい。
