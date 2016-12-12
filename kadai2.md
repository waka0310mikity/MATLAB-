# 課題２レポート
標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。  

ORG = rgb2gray(ORG); colormap(gray); colorbar;
imagesc(ORG); axis image;

によって、読み込んだ画像をグレースケールし表示した結果を図1に示す。また、これを原画像とする。  

![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai2IMG1.PNG "原画像の表示")  
図１　原画像の表示

原画像を2階調にするには、しきい値を一つ定めればよい。

IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image;  

2階調画像を図2に示す。  

![2階調画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai2IMG2.PNG "2階調画像")  
図2　2階調画像  

次に、原画像を4階調にするにはしきい値を四つ定める。  

IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;
imagesc(IMG); colormap(gray); colorbar;  axis image;  

4階調画像を図3に示す。  

![4階調画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai2IMG3.PNG "4階調画像")  
図3　4階調画像  
