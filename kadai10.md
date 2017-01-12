#課題10レポート
___
% 課題10 画像のエッジ抽出   
% 次のプログラムを参考にして，エッジ抽出を体験せよ．  
% 各自，Lenna以外の画像を用いよ．
___
エッジ抽出で「プレウィット法」,「ソベル法」,「キャニー法」を確認する.  
原画像を読み込み,白黒濃淡画像へ変換させる.

ORG = imread('mika.jpg'); % 原画像の入力

![現画像](https://github.com/fujikawabata/MATLAB/blob/master/image/mika.jpg)
図1　原画像

ORG = rgb2gray(ORG); %カラーからグレイへの変換  
imagesc(ORG); colormap('gray'); colorbar;% 画像表示

![現画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai10/kadai10-1.jpg)
図2　白黒濃淡画像

エッジ抽出を各手法で確認する.
まず「プレウィット法」を確認する.この方法では微分係数にプレウィット近似を使用してエッジを検出する.ORGの勾配が最大である点のエッジを返す.  
「プレウィット法」によるエッジ抽出は以下のように記述する.

IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）

結果を図3に示す.
![現画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai10/kadai10-2.jpg)
図3　プレウィット法による画像

「ソベル法」を確認する.この方法では微分係数にソベル近似を使用してエッジを検出する.ORGの勾配が最大である点のエッジを返す.  
「ソベル法」によるエッジ抽出は以下のように記述する.

IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）

結果を図4に示す.
![現画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai10/kadai10-3.jpg)
図4　ソベル法による画像

「キャニー法」を確認する.この方法では強いエッジと弱いエッジを検出するために 2 つのしきい値が使用される.強いエッジと連結している場合にのみ,弱いエッジも出力される.  
「キャニー法」によるエッジ抽出は以下のように記述する.

IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）

結果を図5に示す.
![現画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai10/kadai10-4.jpg)
図5　キャニー法による画像

以上でエッジ抽出を各方法で確認した.なおキャニー法は,2 つのしきい値を使用することにより他の方法よりノイズの影響を受けにくく,弱いエッジを正確に検出できる可能性が高くなる.
