#課題2レポート

以下の原画像は,ディジタルグレースケール画像である.「rgb2gray」とすることでカラー画像をグレースケール画像にできる.画像の表示はグレースケールにするので,カラーマップの表示を設定する「colormap」をgrayにすればグレースケール画像が表示される.

ORG=imread('ramen.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;

によって原画像を読み込み,モノクロで表示する.

![原画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai2/ramen.jpg?raw=true)  
図1 原画像

グレースケールは256階調あるので,2階調は原画像を0~127と128~255の2つの階調で分けることで表現できる.よって

IMG = ORG>128;  
imagesc(IMG); colormap(gray); colorbar;  axis image;

と記述することで2階調画像を表現できる.  
2階調画像を図2に示す.

![2階調](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai2/kadai2-1.jpg?raw=true)  
図2 2階調画像

4階調は階調を0~63,64~127,128~191,192~255で分けることで表現できる.よって

IMG0 = ORG>64;  
IMG1 = ORG>128;  
IMG2 = ORG>192;  
IMG = IMG0 + IMG1 + IMG2; 

と記述することで4階調画像が表現できる.  
4階調画像を図3に示す.

![4階調画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai2/kadai2-2.jpg?raw=true)  
図3 4階調画像

8階調は階調を0~31,32~63,64~95,96~127,128~159,160~191,192~223,224~255で分けることで表現できる.よって

IMG0 = ORG>32;  
IMG1 = ORG>64;  
IMG2 = ORG>96;  
IMG3 = ORG>128;  
IMG4 = ORG>160;  
IMG5 = ORG>192;  
IMG6 = ORG>224;  
IMG = IMG0+IMG1+IMG2+IMG3+IMG4+IMG5+IMG6;

で8階調画像が表現できる.  
8階調画像を図4に示す.

![8階調画像](https://github.com/fujikawabata/MATLAB/blob/master/image/kadai2/kadai2-2.jpg?raw=true)  
図4 8階調画像

以上のように記述することで2階調,4階調,8階調の画像が生成される.
