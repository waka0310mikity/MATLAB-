# 課題１レポート
標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。  

ORG=imread('flower.jpg'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，表示した結果を図１に示す．  

![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai1IMG1.PNG "原画像の表示")  
図１　原画像の表示

原画像を1/2サンプリングするには、画像を1/2倍に縮小した後、2倍に拡大すればよい。なお、拡大する際には、単純補完するために[box]オプションを設定する。  

IMG = imresize(ORG,0.5); %画像の縮小  
IMG2 = imresize(IMG,2,'box'); %画像の拡大  

1/2サンプルの結果を図2に示す。  
<div style="text-align: center;">
![1/2サンプリング](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai1IMG2.PNG "1/2サンプリング")  
図2　1/2サンプリング
</div>
同様に、原画像を1/4サンプリングするには、画像を1/2倍に縮小した後、2倍に拡大すればよい。すなわち、  

IMG = imresize(ORG,0.5); %画像の縮小  
IMG2 = imresize(IMG,2,'box'); %画像の拡大  

とする。1/4サンプリングの結果を図3に示す。  

<div style="text-align: center;">
![1/4サンプリング](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai1IMG3.PNG "1/4サンプリング")  
図3　1/4サンプリング
</div>

1/8から1/32サンプリングも同様に  

IMG = imresize(ORG,0.5); %画像の縮小  
IMG2 = imresize(IMG,2,'box'); %画像の拡大  

を繰り返す。サンプリング結果を図4、5、6に示す。

<div style="text-align: center;">
![1/8サンプリング](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai1IMG4.PNG "1/8サンプリング")  
図4　1/8サンプリング  

![1/16サンプリング](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai1IMG5.PNG "1/16サンプリング")  
図5　1/16サンプリング  

![1/32サンプリング](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai1IMG6.PNG "1/32サンプリング")  
図6　1/32サンプリング  
</div>

このようにサンプリング幅が大きくなると、モザイク状のサンプリング歪みが発生する。
