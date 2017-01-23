#課題４レポート
___
% 課題４　画像のヒストグラム  
% 画素の濃度ヒストグラムを生成せよ．  
% 課題作成にあたっては「Lenna」以外の画像を用いよ．
___

原画像はディジタルカラー画像である.まず原画像を読み込む.

ORG=imread('ramen.jpg'); % 原画像の入力 

読み込んだ原画像を図1に示す.
![原画像](https://github.com/fujikawabata/MATLAB/raw/master/image/ramen.jpg?raw=true)
図1　原画像

白黒濃淡画像へ変換させるために以下の記述をする.

ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;

白黒濃淡画像を図2に示す.
![原画像](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai4/kadai4-1.jpg?raw=true)
図2　白黒濃淡画像

次に以下の記述をすることで,画素の濃度ヒストグラムが生成できる.

imhist(ORG); % ヒストグラムの表示

![原画像](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai4/kadai4-2.jpg?raw=true)  
図3 濃度ヒストグラムの画像  

なお濃度ヒストグラムの縦軸は濃度数,横軸は濃度値を表している.

以上で画素の濃度ヒストグラムを生成できた.
