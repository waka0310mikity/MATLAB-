# 課題9レポート
メディアンフィルターを適用し，ノイズ除去を体験せよ  

## プログラム
[kadai9.m](https://github.com/waka0310mikity/MATLAB-/blob/master/kadai9.m)  

標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。

`ORG = imread('flower.JPG');`  
`ORG = rgb2gray(ORG);`  
`imagesc(ORG); colormap('gray'); colorbar;`

によって、読み込んだ画像をグレースケールし表示した結果を図1に示す。また、これを原画像とする。  

![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai9IMG1.PNG "原画像の表示")  
図1　原画像の表示

`ORG = imnoise(ORG,'salt & pepper',0.02);`  
ノイズ「solt&pepper」を画像に添付。

![ノイズ添付画像](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai9IMG2.PNG "ノイズ添付画像")  
図2　ノイズ添付画像

`IMG = filter2(fspecial('average',3),ORG);`  
ノイズを平滑化フィルタで除去。

![平滑化フィルタ](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai9IMG3.PNG "平滑化フィルタ")  
図3　平滑化フィルタ

`IMG = medfilt2(ORG,[3 3]);`
ノイズをメディアンフィルタで除去。

![メディアンフィルタ](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai9IMG4.PNG "メディアンフィルタ")  
図4　メディアンフィルタ

`f=[0,-1,0;-1,5,-1;0,-1,0];
IMG = filter2(f,IMG,'same');`
高域強調フィルタを設計し、適用。

![高域強調フィルタ](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai9IMG5.PNG "高域強調フィルタ")  
図5　高域強調フィルタ

## 考察
図3の平滑化フィルタを適用した画像と図4のメディアンフィルタを適用した画像を比較すると、図3はノイズが完全に除去できていないこと、また、エッジがぼけていることがわかる。  
対して図4ではエッジがぼけることなく、ノイズも完全に除去されている。  
また、高域強調フィルタを適用した図5において、花の輪郭部が強調させた。
