# EMUZ80-1802RAM

![MEZ1802RAM](https://github.com/satoshiokue/EMUZ80-1802RAM/blob/main/CPD1802ACD.jpeg)  
1802 Single-Board Computer

電脳伝説さん(@vintagechips)のEMUZ80が出力するZ80 CPU信号をメザニンボードで組み替え、CDP1802を動作させることができます。  
  
EMUZ80-1802RAMはCDP1802のメモリー空間が全てSRAMのシステムです。  
EMUZ80のリセットボタンが押されるとCDP1802をLOADモードにして、PICに保存されているROMイメージをSRAMにDMAします。  
リセット時にEMUZ80基板のUARTコネクタから9600bpsでメッセージが出力されます。  
```
MEZ1802RAM 3.200MHz
```
MEZ1802RAM基板のコネクタはソフトウェアシリアルで使用されます。  

ソースコードは電脳伝説さんのEMUZ80用main.cを元に改変してGPLライセンスに基づいて公開するものです。  

## メザニンボード
https://github.com/satoshiokue/MEZ1802RAM  

## ファームウェア

EMUZ80で配布されているフォルダemuz80.X下のmain.cと置き換えて使用してください。
* emuz80_1802RAM.c

## 動作確認用のPICプログラムの書き込み
EMUZ80技術資料8ページにしたがってPICに適合するemu1802RAM_Qxx.hexファイルを書き込んでください。  

またはArduino UNOを用いてPICを書き込みます。  
https://github.com/satoshiokue/Arduino-PIC-Programmer

## 1802プログラムの格納
インテルHEXデータを配列データ化して配列rom[]に格納すると1802で実行できます。

配列に格納するROMデータは16KByteで分割してください。  
テキスト変換例
```
xxd -i -c16 MCSMP20A.bin > MCSMP20A.txt
```
The 1802 Membership Card  
https://www.sunrise-ev.com/1802.htm  

## 参考）EMUZ80
EUMZ80はZ80CPUとPIC18F47Q43のDIP40ピンIC2つで構成されるシンプルなコンピュータです。

![EMUZ80](https://github.com/satoshiokue/EMUZ80-6502/blob/main/imgs/IMG_Z80.jpeg)

電脳伝説 - EMUZ80が完成  
https://vintagechips.wordpress.com/2022/03/05/emuz80_reference  
EMUZ80専用プリント基板 - オレンジピコショップ  
https://store.shopping.yahoo.co.jp/orangepicoshop/pico-a-051.html

## 参考）phemu6809
comonekoさん(@comoneko)さんがEMUZ80にMC6809を搭載できるようにする変換基板とファームウェアphemu6809を発表されました。

![phemu6809](https://github.com/satoshiokue/EMUZ80-6502/blob/main/imgs/IMG_6809.jpeg)

https://github.com/comoneko-nyaa/phemu6809conversionPCB  
phemu6809専用プリント基板 - オレンジピコショップ  
https://store.shopping.yahoo.co.jp/orangepicoshop/pico-a-056.html

