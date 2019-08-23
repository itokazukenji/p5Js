# p5Js

```bash
"use strict";

var setup = function setup() { // 準備
  createCanvas(300, 300); // キャンバスのサイズ
  frameRate(50); // 1秒間に何回フレーム（画面）を置き換えるか
};

var num = 0; // フレームの偶数回、奇数回を判断するために変数を作る

var draw = function draw() { // 描画
  if (mouseIsPressed) { // マウスをクリックしている間の処理はここから、この中がループします。
    var rand1 = random(50, 150); // ここでは８つの変数を作ります。
    var rand2 = random(50, 150); // 最初の4つは上にビビビっと行くように
    var rand3 = random(50, 150); // 後の4つは下にビビビっと行くように
    var rand4 = random(50, 150); // 最初の4つはランダムに５０〜１５０の数値が選ばれます
    var rand5 = random(150, 250); //後の4つは１５０〜250の数値がランダムに
    var rand6 = random(150, 250);
    var rand7 = random(150, 250);
    var rand8 = random(150, 250);

    if (num % 2 == 0) { //フレームが偶数回目の時
      clear(); // 一旦描画をクリア
      line(0, 150, 40, 150); // ここから座標点を指定していきそれらが線で繋がる仕組みです
      line(40, 150, 60, rand1); // 線をジグザグの上下に結んでいきたいので
      line(60, rand1, 90, rand5); // 最初の4つの変数と後の4つの変数が交互に入ります
      line(90, rand5, 120, rand2);
      line(120, rand2, 150, rand6);
      line(150, rand6, 180, rand3);
      line(180, rand3, 210, rand7);
      line(210, rand7, 240, rand4);
      line(240, rand4, 260, 150);
      line(260, 150, 300, 150);
    } else { // ここからは奇数回目の時、偶数の時とは逆になります。
      clear();
      line(0, 150, 40, 150);
      line(40, 150, 60, rand5);
      line(60, rand5, 90, rand1);
      line(90, rand1, 120, rand6);
      line(120, rand6, 150, rand2);
      line(150, rand2, 180, rand7);
      line(180, rand7, 210, rand3);
      line(210, rand3, 240, rand8);
      line(240, rand8, 260, 150);
      line(260, 150, 300, 150);
    }
    num++; // 偶数回、奇数回を判断するため変数に1を加えていきます
  } else { // マウスのクリックが終わった状態
    clear(); 
    line(0, 150, 300, 150); // 単なる直線を描画
    num = 0; // 変数を0に戻します。
  }
};
```
