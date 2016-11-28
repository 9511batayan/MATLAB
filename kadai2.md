#課題2レポート

以下の原画像は,縦1120画素,横840画素のディジタルモノクロ画像である.

ORG=imread('ramen.jpg'); % 原画像の入力
ORG = rgb2gray(ORG); colormap(gray); colorbar;
imagesc(ORG); axis image; % 画像の表示

によって原画像を読み込み,モノクロで表示する｡

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai2/ramen.jpg?raw=true)  
図1 原画像

2階調は
