# 課題6レポート  

標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。

ORG = rgb2gray(ORG); colormap(gray); colorbar;  
imagesc(ORG); axis image;

によって、読み込んだ画像をグレースケールし表示した結果を図1に示す。また、これを原画像とする。

![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai6IMG1.PNG "原画像の表示")  
図１　原画像の表示

IMG = ORG>128;  
imagesc(IMG); colormap(gray); colorbar;  

によって閾値128で二値化する。  

![閾値128での二値化画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai6IMG2.PNG "閾値128での二値化画像")  
図２　閾値128での二値化画像

IMG = dither(ORG);  
imagesc(IMG); colormap(gray); colorbar;  

によってディザ法で二値化する。

![ディザ法での二値化画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai6IMG3.PNG "ディザ法での二値化画像")  
図３　ディザ法での二値化画像  
