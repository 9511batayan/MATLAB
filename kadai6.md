#課題6レポート

画像を2値化させるために閾値を指定して2値化させる手法とディザ法による2値化を用いる.  
まず原画像を読み込む.

ORG=imread('ramen.jpg'); % 原画像の入力

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/ramen.jpg)
図1　原画像

白黒濃淡画像へ変換させる.そのために以下の記述をする.

ORG = rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai6/kadai6-1.jpg)
図2　白黒濃淡画像



