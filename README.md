# Windows Open Notifier Docker

## これは何？
[Window Open Notifier](https://github.com/Mekapiku/window-open-notifier)をDockerで動かすやつです．

## 使い方
```
docker build -t window-open-notifier/window-open-notifier .
docker run --rm -e IPHONE_IP="192.168.1.70" \
                -e VNC_PASSWD_FILE="/data/vnc_passwd" \
                -e OUTPUT_FILE="/tmp/leafee.json"
                -e SOURCE_IMG="/tmp/screenshot.jpg"
                -e LEAFEE_SIZE="3" \
                -v /data:/data \
                -v /tmp:/tmp \
                --name window-open-notifier \
                window-open-notifier/window-open-notifier
```

## 出力結果(例)
```
{
    "leafee": [
        {
            "id": 0,
            "state": "locked"
        },
        {
            "id": 1,
            "state": "locked"
        },
        {
            "id": 2,
            "state": "locked"
        }
    ]
}
```

## 環境変数
`IPHONE_IP` Leafeeアプリを動かしているiPhoneのIPアドレス

`VNC_PASSWD_FILE` `vncpasswd`コマンドで生成したファイルパス

`OUTPUT_FILE` 結果の出力先：デフォルト`/tmp/leafee.json`

`SOURCE_IMG` `vncsnapshot`コマンドで取得されたスクリーンショット保存先：デフォルト`/tmp/screenshot.jpg`

`LEAFEE_SIZE` Leafee magの利用数

## その他
[Leafeeシングルプラン](https://leafee.me/price)に加入したほうが早いし安いし便利です．
