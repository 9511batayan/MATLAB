図1を原画像とする。この画像は縦1920画像，横1434画素のディジタルカラー画像である．

ORG=imread('ramen.jpg'); % 原画像の入力
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，表示した結果を図１に示す．

![原画像](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/ramen.jpg?raw=true)
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

![1/4サンプリング](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/kadai1-2.jpg?raw=true)
図3　1/4サンプリング画像

1/8サンプリングするには,図3の画像を1/2に縮小した後,8倍に拡大させればいい.よって

IMG = imresize(IMG,0.5); % 画像の縮小
IMG2 = imresize(IMG,8,'box'); % 画像の拡大

とする.1/8サンプリングの結果を図4に示す.

![1/8サンプリング](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/kadai1-3.jpg?raw=true)
図3　1/8サンプリング画像

1/16,1/32,1/64サンプリングも同様に

IMG = imresize(IMG,0.5); % 画像の縮小
IMG2 = imresize(IMG,16,'box'); % 画像の拡大

IMG = imresize(IMG,0.5); % 画像の縮小
IMG2 = imresize(IMG,32,'box'); % 画像の拡大

IMG = imresize(IMG,0.5); % 画像の縮小
IMG2 = imresize(IMG,64,'box'); % 画像の拡大

とすることで,ダウンサンプリングできる.結果を図5~7に示す.

![1/16サンプリング](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/kadai1-4.jpg?raw=true)
図3　1/16サンプリング画像

![1/32サンプリング](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/kadai1-5.jpg?raw=true)
図3　1/32サンプリング画像

![1/64サンプリング](https://github.com/fujikawabata/MATLAB/raw/master/image/kadai1/kadai1-6.jpg?raw=true)
図3　1/64サンプリング画像

このようにサンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生することが分かる.
