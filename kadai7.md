#課題7レポート
___
% 課題7　ダイナミックレンジの拡大  
% 画素のダイナミックレンジを０から２５５にせよ．   
% 課題作成にあたっては「Lenna」以外の画像を用いよ． 
___
画像の最高濃度と最低濃度の差が小さい場合,コントラストの低い見づらい画像になる.これを解決するために,濃度値の全領域を利用できるように画像の濃度値を変換しダイナミックレンジの拡大を行う.ダイナミックレンジを0から255に設定するためにまず原画像を読み込む.

ORG = imread('house.jpg'); % 画像の読み込み

原画像は図1である.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/house.jpg)
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

以下の記述をすることでダイナミックレンジの拡大ができる.

ORG = double(ORG);  
mn = min(ORG(:)); % 濃度値の最小値を算出  
mx = max(ORG(:)); % 濃度値の最大値を算出  
ORG = (ORG-mn)/(mx-mn)*255;  

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai7/kadai7-3.jpg)
図4　ダイナミックレンジの拡大した後の画像

「uint8」は8 ビット符号なし整数への変換で用いる.「uint8」を用いるのは拡大する範囲が2^8乗であるためである.これを用いることでダイナミックレンジの拡大による全領域の濃度値を表示できる.

ORG = uint8(ORG);

ダイナミックレンジの拡大した後の濃度ヒストグラムを見るために以下の記述をする.

imhist(ORG); % 濃度ヒストグラムを生成、表示

結果を図4に示す.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai7/kadai7-4.jpg)
図5　ダイナミックレンジの拡大した後の濃度ヒストグラム

画像を比較すると,図2では屋根など暗く見づらかった部分が図3では多少明るくなり見やすいことがわかり,濃度ヒストグラムにするとダイナミックレンジが拡大できたことが確認できる.
