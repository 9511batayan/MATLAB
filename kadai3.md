#課題3レポート

原画像はディジタルカラー画像である.その原画像を白黒濃淡画像へ変換させる.
以下の記述をして変換し,画像を表示させる.

ORG=imread('ramen.jpg'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/課題3/ramen.jpg?raw=true)  
図1 白黒濃淡画像

