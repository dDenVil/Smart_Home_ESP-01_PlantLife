# Smart Home on ESP-01. PlantLife Project
Hey there 👋 This is my 2nd project on GitHub    
Project made for my little succulents with help of relay module and ESP-01 on it

## Problem

Few years ago I found a new hobby [florariums](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/Readme_assets/IMG_20210118_213639_155.jpg?raw=true). I was making them one by one, and with them came [succulents](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/Readme_assets/IMG_20201107_133931.jpg?raw=true). This plants require a lot of light so I was forced to make sothing like this. [Stand with led strips](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/Readme_assets/IMG_20210830_010725.jpg?raw=true).

![Plants Stand with light](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/Readme_assets/IMG_20211005_163648.jpg?raw=true)

Lately I changed its format factor to
[stand for plants with light v2](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/Readme_assets/IMG_20220910_150751.jpg?raw=true).
But I was left with the main problem - light time. I had to turn onoff it every morning and evening. So I came up with the idea of automatic light that can can be controlled by phone.   

## Results
So what functionality I have got:
- Telegram BOT
- Auto and Manual mode
- Timezone settings
- Saving parameters to EEPROM (after restarting it remembers it's mode, work timer and timezone)
- ONLINE notifications

As you can see I've got everything I wanted, and even more. In Ukraine in this times, notification "ONLINE" helps me to know whether I have light at home or not. I can change mode, working time, timezone

![Plants Stand with light](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/Readme_assets/photo_2022-12-06_00-21-12.jpg?raw=true)

## Getting started
We will need relay module with ESP-01 and any step down conventer 

![relay module](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/Readme_assets/relay.png?raw=true)

- Create telergam bot
  - Search for [@BotFather](https://t.me/BotFather)
  - /start -> /newbot -> .... -> copy  the HTTP API
- Get your own Telegram ID from [@username_to_id_bot](https://t.me/username_to_id_bot)
- Change the code
```c
// Wifi network station credentials
#define WIFI_SSID "YOUR_SSID"
#define WIFI_PASSWORD "PASS"
// Telegram BOT Token (Get from Botfather)
#define BOT_TOKEN "YOUR_BOT_TOCKEN"
#define CHAT_ID "YOUR_TELEGRAM_ID"
```
- Load the code to ESP-01
  - Connect to TTL-conventer ([scheme](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/Readme_assets/esp01.png?raw=true))
  - In Arduino IDE go to references and add additional board manager URL `http://arduino.esp8266.com/stable/package_esp8266com_index.json`
  - Add board to the Arduino IDE (Tools->Board->Board Manager->`ESP8266`)
  - Choose correct board and Port (Tools->Board->ESP8266->Generic ESP8266 Module)
  - Install [Telegram Bot Library](https://github.com/witnessmenow/Universal-Arduino-Telegram-Bot) (Sketch->Include library->Add .ZIP library)
  - Start the ESP in flash mode (short GPIO0 and GND) and load the [code](code.txt)
- Connect everything together
  - to power up the relay [module](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/Readme_assets/relay.png?raw=true) connect it to the [step-down conventer](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/Readme_assets/dc-dc-dsn-mini-360-01.jpg?raw=true)
  - Connect by the [scheme](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/scheme.png?raw=true)
- Power up and in the telegram set your timezone, work mode... of your system
- Done ;D

![plant life](https://github.com/dDenVil/Smart_Home_ESP-01_PlantLife/blob/main/Readme_assets/phone.jpg?raw=true)

