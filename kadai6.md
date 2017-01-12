#課題6レポート
___
% 課題６　画像の二値化  
% 下記のプログラムを参考にして画像を二値化せよ．  
% 課題作成にあたっては「Lenna」以外の画像を用いよ．  
画像を2値化させるために閾値を指定して2値化させる手法とディザ法による2値化を用いる.  
___
まず原画像を読み込む.

ORG=imread('ramen.jpg'); % 原画像の入力

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/ramen.jpg)
図1　原画像

読み込んだ原画像を白黒濃淡画像へ変換させる.

ORG = rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai6/kadai6-1.jpg)
図2　白黒濃淡画像

閾値を128に指定し,128より大きい値を1,それ以下を0に変換させて2値化させる.

IMG = ORG>128; % 128による二値化

閾値による2値化の結果を図3に示す.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai6/kadai6-2.jpg)
図3　128による2値化画像

ディザ法による2値化を行う.ディザ法は輝度が0と255の色だけを用いて中間色を表現する手法である.具体的には点の密度が大きい所は濃く見え,小さい所は薄く見えることを利用している.ディザ法を用いる場合

IMG = dither(ORG); % ディザ法による二値化  

と記述する.結果を図4に示す.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai6/kadai6-3.jpg)
図4　128による2値化画像

以上で画像を2値化させた.
