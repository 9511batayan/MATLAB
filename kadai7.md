#課題7レポート
___
% 課題7　ダイナミックレンジの拡大  
% 画素のダイナミックレンジを０から２５５にせよ．   
% 課題作成にあたっては「Lenna」以外の画像を用いよ． 
___
ダイナミックレンジの拡大は
まず原画像を読み込む.

ORG = imread('mika.jpg'); % 画像の読み込み

原画像は図1である.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/mika.jpg)
図1　原画像

読み込んだ原画像を白黒濃淡画像に変換する.

ORG = rgb2gray(ORG); % 白黒濃淡画像に変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

白黒濃淡画像は図2のようになる.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai7/kadai7-1.jpg)
図2　白黒濃淡画像

imhist(ORG); % 濃度ヒストグラムを生成、表示

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai7/kadai7-2.jpg)
図3　濃度ヒストグラム

ORG = double(ORG);  
mn = min(ORG(:)); % 濃度値の最小値を算出  
mx = max(ORG(:)); % 濃度値の最大値を算出  
ORG = (ORG-mn)/(mx-mn)*255;  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai7/kadai7-3.jpg)
図4　ダイナミックレンジの拡大した後の画像

ORG = uint8(ORG);


imhist(ORG); % 濃度ヒストグラムを生成、表示

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai7/kadai7-4.jpg)
図5　ダイナミックレンジの拡大した後の濃度ヒストグラム

画像を表示しただけでは分からないが,濃度ヒストグラムにするとダイナミックレンジが拡大できたことが確認できる.
