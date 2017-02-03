# ifttt_with_sensor_rpi
IFTTT makerチャネルを利用したsensorデータの収集

# How to use
## IFTTTでAppletを作成
MakerサービスをThisに設定し"Receive a web request"をTriggerに動くAppletを作成する
## IFTTTのMakerチャネル
https://ifttt.com/services/maker/settings を開いて`https://maker.ifttt.com/use/{maker_key}` のmaker_keyを取得
## iftttで設定したイベント名を確認しておく

## 環境変数を設定し、実行する
環境変数を２つ設定する

```
$ export maker_key={{ifttt_maker_channel}}
$ export maker_event_store_sensor={{ifttt_event_name}}
```

実行する
```
$ python3 ifttt_with_sensor_rpi.py
```

## 実行
10秒ごとにiftttのmakerがトリガされます。
Makerサービスを利用して３つ値が渡せるので以下を渡している。
value1はRPiの現在時刻
value2はGPIO17の値
value3はI2Cで温度センサの値

