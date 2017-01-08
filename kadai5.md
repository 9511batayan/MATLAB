#課題5レポート

判別分析法は分離度と呼ばれる値が最大となる閾値を求め,自動的に2値化を行う手法である.分離度はクラス間分散とクラス内分数の比で求められる.  
まず原画像を読み込み白黒濃淡画像に変換させる.原画像はディジタルカラー画像である.

ORG=imread('ramen.jpg'); % 原画像の入力

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/ramen.jpg)
図1　原画像

原画像を白黒濃淡画像に変換するために以下の記述をする.

ORG = rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;

![白黒濃淡画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai5/kadai5-1.jpg)
図2　白黒濃淡画像
