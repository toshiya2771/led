# myled
ロボットシステム学の講義で作成したデバイスドライバ

# 内容
これは、ロボットシステム学の講義で作成したデバイスドライバに一部変更を加えたものです。
講義ではechoに0と1をつけることでLEDの点灯と消灯を行うデバイスドライバを作成しました。
そこに私はecho2を加えました。
echo2をするとLEDの光を利用したモールス信号でavalancheという英語を作り出します。

# 必要なもの
Raspberry Pi 4 Model B  
ブレッドボード x1  
ジャンパー線 x2  
抵抗（Φ5） x1  
LED(青色) x1  

# 回路
ラズパイ4GPIOピン配置  
![SnapCrab_NoName_2021-12-15_15-53-3_No-00](https://user-images.githubusercontent.com/92073288/148357576-5b8ac453-5ed0-427e-a404-ce6196adcb66.png)  
今回はLEDのアノード側はGPIO25番ピンにさし、カソード側は画像の30のGNDにさしています。

# 前準備
$ make  
$ sudo insmod myled.ko  
$ sudo chmod 666 /dev/myled0  

# 実行
前準備のコマンドを打ち終わったら以下のコマンドを実行します。  
$ echo 1 > /dev/myled0  
このコマンドを打つとLEDが光り続けます。  

$ echo 0 > /dev/myled0  
このコマンドを打つと光っているLEDの光を消します。  

$ echo 2 > /dev/myled0  
このコマンドを打つとモールス信号でavalancheと表します。  
これ以外の数字を入力した場合、何も起こりません。

# 動画  

            https://youtu.be/oFk4M1rE1HE
          
youtubeに動画を上げてあります  

# 参考リンク
モールス信号  
https://www.benricho.org/symbol/morse.html  
GPIOピン配置  
https://www.raspberrypi.com/documentation/computers/os.html  

# ライセンス
[GNU General Public License v3.0](https://github.com/toshiya2771/led/blob/main/COPYING)


　
