# arduino_kw1281_softwareserial
ArduinoUnoR3にて標準ライブラリのSoftwareSerialを使用したKW1281によるECUとの通信スケッチです。<br>
コードは下記ALEXANDER GRAU様のコードほぼそのままですが、同梱の古いNewSoftwareSerialではなく、IDE標準のSoftwareSerialを使用して動くように修正しました。<br>
http://grauonline.de/wordpress/?p=74

変更箇所はobd.flush();をwhile (obd.available() > 0) obd.read();に書き換え、obd.write(data);の前にdelay(5);を入れてあるだけです。<br>
SoftwareSerialで動かなかった原因のほとんどは、NewSoftwareSerialとSoftwareSerialでflushの動作が変更されてしまったことにあるようです。<br>
https://forum.arduino.cc/t/softwareserial-flush-broken/114180

私はこのコードは直接使用したわけではなく、UnoR3での初期動作検証にしか使用していないのでLiquidCrystalの同梱ライブラリは触っていません。<br>
上手くすればLiquidCrystalも同梱ライブラリで動かせると思いますし、そうすればスケッチ自体一つのファイルでスマートに管理できると思います。<br>
また通信テストもPolo 9N3のECUをベンチケーブルでつないでテストしただけですので、実車両で正常に動くかはわかりません。<br>
使う方は自己責任でお願いします。<br>
ALEXANDER GRAU様に謝辞を申し上げます。
