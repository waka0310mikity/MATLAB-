# 課題10レポート
エッジ抽出を体験せよ。  

## プログラム
[kadai10.m](https://github.com/waka0310mikity/MATLAB-/blob/master/kadai10.m)  

標準画像「flower」を原画像とする。これは1040画素×1040画素の正方形のディジタルカラー画像である。

`ORG = imread('flower.JPG');`  
`ORG = rgb2gray(ORG);`  
`imagesc(ORG); colormap('gray'); colorbar;`

によって、読み込んだ画像をグレースケールし表示した結果を図1に示す。また、これを原画像とする。

![原画像の表示](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai10IMG1.PNG "原画像の表示")  
図1　原画像の表示

`IMG = edge(ORG,'prewitt')`  
プレウィット法にてエッジ抽出を行う。

![プレウィット法](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai10IMG2.PNG "プレウィット法")  
図2　プレウィット法

`IMG = edge(ORG,'sobel')`  
ソルベ法によってエッジ抽出を行う。

![ソルベ法](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai10IMG3.PNG "ゾルべ法")  
図3　ゾルべ法

`IMG = edge(ORG,'canny');`  
キャニー法にてエッジ抽出を行う。

![キャニー法](https://github.com/waka0310mikity/MATLAB-/blob/master/images/kadai10IMG4.PNG "キャニー法")  
図4　キャニー法

## 考察
プレウィット法は3画素ずつを対にして濃度の変化点を抽出する処理である。  
ソルベ法はプレウィット法において、中心画素の影響を強調したもの。  
従って、図2と図3を比較すると2つの画像間に大きな差異はない。  
キャニー法は非極大値の抑制を行いエッジと関係ない画素を取り除き、ヒステリシス(Hysteresis)を使ったしきい値処理を行う。そのため、より正確なエッジ抽出を行うことができ、図4は図2、図3と比較し輪郭部がよりはっきりしているとみることができる。
