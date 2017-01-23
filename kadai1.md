#課題1レポート
___
課題内容  
% 課題１　標本化間隔と空間解像度  
% 画像をダウンサンプリングして（標本化間隔を大きくして）  
% 表示せよ．  
% 課題作成にあたっては「Lenna」以外の画像を用いよ．
___

以下の原画像はディジタルカラー画像である．  

ORG=imread('ramen.jpg'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，表示した結果を図１に示す．
![原画像](https://github.com/fujikawabata/MATLAB/raw/master/image/ramen.jpg?raw=true)
図1　原画像

原画像を1/2サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．なお，拡大する際には，単純補間するために「box」オプションを設定する．　　

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

1/2サンプリングの結果を図２に示す．

![1/2サンプリング](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/kadai1-1.jpg?raw=true)
図2　1/2サンプリング画像

1/4サンプリングするには,図2の画像を1/2に縮小した後,4倍に拡大させればいい.よって

IMG = imresize(IMG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,4,'box'); % 画像の拡大

とする.1/4サンプリングの結果を図3に示す.

![1/4サンプリング](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/kadai1-2?raw=true)
図3　1/4サンプリング画像

1/8サンプリングするには,図3の画像を1/2に縮小した後,8倍に拡大させればいい.よって

IMG = imresize(IMG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,8,'box'); % 画像の拡大

とする.1/8サンプリングの結果を図4に示す.

![1/8サンプリング](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/kadai1-3.jpg?raw=true)
図4　1/8サンプリング画像

1/16,1/32,1/64サンプリングも同様に記述すればそのサンプリング幅に応じてダウンサンプリングができる.　　

IMG = imresize(IMG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,16,'box'); % 画像の拡大

IMG = imresize(IMG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,32,'box'); % 画像の拡大

IMG = imresize(IMG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,64,'box'); % 画像の拡大  

各サンプリング幅の結果を図5~7に示す.

![1/16サンプリング](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/kadai1-4.jpg?raw=true)
図5　1/16サンプリング画像

![1/32サンプリング](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/kadai1-5.jpg?raw=true)
図6　1/32サンプリング画像

![1/64サンプリング](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/kadai1-6.jpg?raw=true)
図7　1/64サンプリング画像

このようにサンプリング幅を指定することで,モザイク状のサンプリング歪みが発生する。サンプリング幅を大きくさせると，モザイク状のサンプリング歪みは大きくなることが確認できる.
