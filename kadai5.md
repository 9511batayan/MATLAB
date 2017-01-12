#課題5レポート
___
% 課題５　判別分析法  
% 判別分析法を用いて画像二値化せよ．  
% 課題作成にあたっては「Lenna」以外の画像を用いよ．
___

判別分析法は分離度と呼ばれる値が最大となる閾値を求め,自動的に2値化を行う手法である.分離度はクラス間分散とクラス内分数の比で求められる.  
まず原画像を読み込み白黒濃淡画像に変換させる.原画像はディジタルカラー画像である.原画像を読み込み,白黒濃淡画像に変換するために以下の記述をする.

ORG=imread('Mika_Rika_2.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;

![白黒濃淡画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai5/kadai5-1.jpg)
図1　白黒濃淡画像

H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納  
myu_T = mean(H);  
max_val = 0;  
max_thres = 1;  

「for i=a:b」で変数iをaからbまで１ずつインクリメントし,bを超えるまで実行を繰り返す処理である.各濃度値を算出したいので1から255までを繰り返すように記述する.

for i=1:255  
C1 = H(1:i); %ヒストグラムを2つのクラスに分ける  
C2 = H(i+1:256);  
n1 = sum(C1); %画素数の算出  
n2 = sum(C2);  
myu1 = mean(C1); %平均値の算出  
myu2 = mean(C2);  
sigma1 = var(C1); %分散の算出  
sigma2 = var(C2);  
sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出  
sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出  

分離度が最大となる閾値を求めればいい.
if max_val<sigma_B/sigma_w  
max_val = sigma_B/sigma_w;  
max_thres =i;  
end;  
end;

分離度が最大となる閾値がmax_thresとなったので,この閾値より大きい濃度値は1,小さい値は0とすればいい.よって

IMG = ORG > max_thres;  
imagesc(IMG); colormap(gray); colorbar;

のように記述すればいい.2値化させた結果を図3に示す.
![白黒濃淡画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai5/kadai5-2.jpg)
図2　判別分析法によって2値化させた画像

以上で判別分析法によって画像を2値化させたことが確認できた.
