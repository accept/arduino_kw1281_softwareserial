# KW1281_Test_ArduinoUnoR3
ArduinoUnoR3にて標準ライブラリのSoftwareSerialを使用したKW1281によるECUとの通信スケッチです。
コードは下記○○様のコードほぼそのままですが、同梱の古いNewSoftwareSerialではなく、IDE標準のSoftwareSerialを使用して動くようにしてあります。

変更箇所はobd.flush();をwhile (obd.available() > 0) {obd.read();}に書き換え、obd.write(data);の前にdelay(5);を入れてあるだけです。
SoftwareSerialで動かなかった原因のほとんどは、NewSoftwareSerialとSoftwareSerialでflsuhの動作が変更されてしまったことに起因するようです。
