#課題3レポート

原画像は図1でディジタルカラー画像である.

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/ramen.jpg?raw=true)  
図1 画像

その原画像を白黒濃淡画像へ変換させる.
以下の記述をして原画像を変換し,画像を表示させる.

ORG=imread('ramen.jpg'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai3/ramen.jpg?raw=true)  
図2 白黒濃淡画像

輝度値を任意に設定することで,閾値処理した画像が表せる.
ここではまず64に設定し,64以上の画素を1,その他を0にすることで閾値処理した画像を表す.
以下の記述をすることで可能となる.

IMG = ORG > 64; % 輝度値が64以上の画素を1，その他を0に変換
imagesc(IMG); colormap(gray); colorbar;

図3に処理した画像を示す.

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai3/kadai3-1.jpg?raw=true)  
図3 輝度値64の閾値処理画像

輝度値を96に設定する｡以下の記述で閾値処理した画像表し,その画像を図4に示す.

IMG = ORG > 96;
imagesc(IMG); colormap(gray); colorbar; % 輝度値が96以上の画素を1，その他を0に変換

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai3/kadai3-2.jpg?raw=true)  
図4 輝度値96の閾値処理画像

輝度値を128に設定する.以下の記述で閾値処理した画像表し,その画像を図5に示す.

IMG = ORG > 128; % 輝度値が128以上の画素を1，その他を0に変換
imagesc(IMG); colormap(gray); colorbar;

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai3/kadai3-3.jpg?raw=true)  
図5 輝度値128の閾値処理画像

輝度値を192に設定する.以下の記述で閾値処理した画像表し,その画像を図6に示す.

IMG = ORG > 192; % 輝度値が192以上の画素を1，その他を0に変換
imagesc(IMG); colormap(gray); colorbar;

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai3/kadai3-4.jpg?raw=true)  
図6 輝度値128の閾値処理画像

以上で閾値を4パターン指定した閾値処理の画像を示した.
