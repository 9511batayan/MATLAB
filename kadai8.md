#課題8レポート
___
% 課題８ ラベリング  
% 二値化された画像の連結成分にラベルをつけよ．  
% 下記はサンプルプログラムである．   
% 課題作成にあたっては「Lenna」以外の画像を用いよ．
___
原画像を読み込み,白黒濃淡画像に変換させる.

ORG = imread('mika.jpg'); % 画像の読み込み

読み込んだ結果を図1に示す.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/mika.jpg)  
図1　原画像

原画像を白黒濃淡画像に変換させる

ORG = rgb2gray(ORG); % 白黒濃淡画像に変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

変換させた結果を図2に示す.

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai8/kadai8-1.jpg)
図2　白黒濃淡画像

2値化された画像にするために閾値を指定して2値化させる.ここでは閾値を128に指定して2値化する.

IMG = ORG > 128; % 閾値128で二値化

2値化した結果を図3に示す.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai8/kadai8-2.jpg)
図3　2値化した画像

2値化された画像の連結部分にラベル付けは「bwlabeln」を用いる.画像を表示するためcolormapは既定のカラーマップにするため「jet」に設定する.

IMG = bwlabeln(IMG);  
imagesc(IMG); colormap(jet); colorbar; % 画像の表示

結果を図4に示す.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai8/kadai8-3.jpg)
図3　2値化した画像の連結部分へのラベル付け

以上で2値化された画像の連結部分にラベルを付けることができた.
