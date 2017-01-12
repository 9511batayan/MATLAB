#課題9レポート
___
% 課題９ メディアンフィルタと先鋭化  
% メディアンフィルターを適用し，ノイズ除去を体験せよ．  
% 各自，Lenna以外の画像を用いよ．
___
メディアンフィルタでノイズ除去を確認するためにまず原画像を読み込み,白黒濃淡画像へ変換させる.原画像の読み込みは

ORG = imread('mika.jpg'); % 画像の読み込み

と記述する.原画像は図1である.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/mika.jpg)
図1　原画像

白黒濃淡画像へ変換させて表示するために

ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

と記述する.変換結果は図2である.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai9/kadai9-1.jpg)
図2　白黒濃淡画像

図2にノイズ添付をする.ノイズのタイプはオンとオフのピクセルであるごま塩ノイズ「salt & pepper」で,ノイズの密度を0.02に設定する.

ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付

添付した結果を図3に示す.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai9/kadai9-2.jpg)
図3　ノイズ添付した画像

メディアンフィルタで除去する前に,比較として平滑化フィルタでまず雑音除去を行う.  
まずフィルタを作成する必要がある.ここでのフィルタの作成には「fspecial('average',hsize)」を用いる.「fspecial('average',hsize)」はサイズhsizeの平均化フィルタを返す.hsizeはh の行数と列数を指定するベクトル,または h が正方行列である場合はスカラーでhsize の既定値は [3 3] であるためここではhsizeを3に設定する.「filter2(h,x)」で行列hのフィルタを用いてxがフィルタ処理される.hには先ほどの「fspecial」を用いる.つまり

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタ

と記述れば平滑化フィルタになる.結果を図4に示す.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai9/kadai9-3.jpg)
図4　平滑化フィルタで雑音除去した画像

メディアンフィルタで雑音除去する.メディアンフィルタ処理は「medfilt2(A,[m,n])」と記述する.ここで各出力ピクセルは、入力イメージ内の対応するピクセル周辺にあるm行n列近傍の中央値を含んでいる.ここでは3行3列近傍の中央値を含ませるつもりなので

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去

と記述する.結果を図5に示す.
![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai9/kadai9-4.jpg)
図5　メディアんフィルタで雑音除去した画像

以上でメディアンフィルタによる雑音処理を確認した.
