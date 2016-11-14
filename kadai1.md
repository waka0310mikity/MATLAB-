# 課題１レポート
標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。  

ORG=imread('flower.jpg'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，表示した結果を図１に示す．  
<div style="text-align: center;">
![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai1IMG1.PNG "原画像の表示")  
図１　原画像の表示
</div>
原画像を1/2サンプリングするには、画像を1/2倍に縮小した後、2倍に拡大すればよい。なお、拡大する際には、単純補完するために[box]オプションを設定する。  

IMG = imresize(ORG,0.5); %画像の縮小  
IMG2 = imresize(IMG,2,'box'); %画像の拡大
