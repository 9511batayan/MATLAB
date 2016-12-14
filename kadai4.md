#課題４レポート
原画像はディジタルカラー画像である.まず原画像を白黒濃淡画像へ変換させる.

ORG=imread('ramen.jpg'); % 原画像の入力
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar;
図2
以下の記述をすることで,画素の濃度ヒストグラムが生成できる.

imhist(ORG); % ヒストグラムの表示

![原画像](https://github.com/fujikawabata/MATLAB/master/image/kadai4/kadai4-2.jpg?raw=true)  
図3 濃度ヒストグラムの画像

以上で画素の濃度ヒストグラムを生成させた.
