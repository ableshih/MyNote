# Telegram Bot

## 產生 bot
    想要一隻 bot 需要先有一個 Telegram 帳號 (電話簡訊驗證)
    私訊 @BotFather
    輸入 /newbot 他將會請您依序輸入 bot 顯示的名稱、 bot 的 username (必須為 bot 結尾) ，且長度需介於 6-32 字元
    完成後， BotFather 會顯示您的 Token (格式: 12345:AAJqs_w-4) ，您可利用此 Token 透過 HTTPS 發送請求

## 用瀏覽器 傳訊
    https://api.telegram.org/bot1031554073:AAGl52W5URoq2ip-8/sendMessage?chat_id=1016366767&text=Hello
    
```
{"ok":true,"result":{"message_id":757,"from":{"id":103155473,"is_bot":true,"first_name":"\u677e\u8208","username":"Gs_Vv_bot"},"chat":{"id":1016366767,"first_name":"\u65bd","last_name":"\u5733\u6eaa","username":"ableshih","type":"private"},"date":1579921380,"text":"Hello"}}
```

## 參考 
https://blog.sean.taipei/2016/10/telegram-bot
https://www.youtube.com/watch?v=-IC-Z78aTOs
* Project Github: 
    https://github.com/witnessmenow/Simple-Home-Automation-With-Telegram
* Telegram Library Github: 
    https://github.com/witnessmenow/Universal-Arduino-Telegram-Bot
* Telegram Group for the library: 
    https://t.me/arduino_telegram_library

## ino
```
char ssid[] = "iPhone";     // your network SSID (name)
char password[] = "0928808"; // your network password
#define TELEGRAM_BOT_TOKEN "1031554073:AAGZANGKGUMl52W5URoq2iYzy7p-i8"
```
