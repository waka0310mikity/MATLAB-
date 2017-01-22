# 課題３レポート
閾値を4パターン設定し,閾値処理た画像を示せ。

## プログラム
[kadai3.m](https://github.com/waka0310mikity/MATLAB-/blob/master/kadai3.m)  
標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。

`ORG = imread('flower.JPG');`  
`ORG = rgb2gray(ORG);`  
`imagesc(ORG); colormap('gray'); colorbar;`

によって、読み込んだ画像をグレースケールし表示した結果を図1に示す。また、これを原画像とする。  

![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai3IMG1.PNG "原画像の表示")  
図１　原画像の表示

輝度値を輝度値が64以上の画素を1，その他を0に変換し閾値処理を行う。　

`IMG = ORG > 64;`  
`imagesc(IMG); colormap(gray); colorbar;`  

実行結果の画像を図２に示す。  

![輝度値64で閾値処理をした画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai3IMG2.PNG "輝度値64で閾値処理をした画像")  
図２　輝度値64で閾値処理をした画像  

次に、輝度値96を閾値とし同様の処理を行う。  

`IMG = ORG > 96;`  
`imagesc(IMG); colormap(gray); colorbar;`  

結果を図３に示す。  

![輝度値96で閾値処理をした画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai3IMG3.PNG "輝度値64で閾値処理をした画像")  
図３　輝度値96で閾値処理をした画像  

次に、輝度値128を閾値とし同様の処理を行う。  

`IMG = ORG > 128;`  
`imagesc(IMG); colormap(gray); colorbar;`  

結果を図４に示す。  

![輝度値128で閾値処理をした画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai3IMG4.PNG "輝度値128で閾値処理をした画像")  
図４　輝度値128で閾値処理をした画像  

次に、輝度値192を閾値とし同様の処理を行う。  

`IMG = ORG > 192;`  
`imagesc(IMG); colormap(gray); colorbar;`    

結果を図５に示す。  

![輝度値192で閾値処理をした画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai3IMG5.PNG "輝度値192で閾値処理をした画像")  
図５　輝度値192で閾値処理をした画像  

## 考察
輝度値は画像の明るさを示す値である。  
輝度値が小さい、すなわち画像中の暗い部分を閾値と定めると、その値より大きい輝度値が多く占める画像ではほとんどが白に変換されてしまう。その反対に、輝度値を大きく定めると低輝度の画像は黒く変換される。  
原画像はおおよそ90から140の輝度値が多いため、その範囲内で閾値処理を行うと見やすい画像が生成されている。  
したがって、輝度値による二値化を行う際はその閾値を原画像の輝度値に合わせて変化させなえればならない。
