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

