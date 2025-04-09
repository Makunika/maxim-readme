## Настраиваем сплит для дискорда

После того, как wg умер - юзаем vless - а его хуй заблокируешь, так как запросы как будто идут по 443 порту (https) на сервера google.

Для него есть клиент - https://github.com/MatsuriDayo/nekoray/releases/tag/4.0.1. Его делали китайцы, а они шарят в способах обхода блокировок. Качаем версию для windows.

![image](https://github.com/user-attachments/assets/59864e7e-d62e-46d0-bda2-b17fb43d3a18)

Качаем, разархивируем, запускаем nekobox.exe

![image](https://github.com/user-attachments/assets/833d71b2-c11e-4178-9638-6ba9dd4a3199)

Привет, интерфейс из 2000х

![image](https://github.com/user-attachments/assets/fb886580-34e5-48cb-8625-63d36560836b)

Итак, настраиваем правила маршрутизации.

1. Переходим в "Настройки" -> "Настройки маршрутов"

![image](https://github.com/user-attachments/assets/b93bf8f9-1255-474d-8706-e59b2d3abc07)

2. "Базовые маршруты". В нем прописываем в IP
   ```
   geoip:ru
   geoip:private
   ```
3. В Outbound ставим `bypass`

![image](https://github.com/user-attachments/assets/7cd2f340-50c1-4295-9433-ce38bc89d2a7)


4. Нажимаем "Кастомные маршруты" и вставляем этот json
```json
{
    "rules": [
        {
            "domain": [
            ],
            "domain_keyword": [
                "yandex",
                "yastatic",
                "yadi.sk",
                "xn--80aswg",
                "xn--d1acpjx3f.xn--p1ai",
                "xn--c1avg",
                "xn--80asehdb",
                "xn--p1acf",
                "xn--p1ai",
                "google.com",
                "gstatic.com",
                "yahoo",
                "bing",
                "tineye",
                "duckduckgo",
                "apple",
                "vk.com",
                "userapi.com",
                "vk-cdn.me",
                "mvk.com",
                "vk-cdn.net",
                "vk-portal.net",
                "vk.cc",
                "icq",
                "livejournal",
                "microsoft",
                "live.com",
                "login.live",
                "tradingview"
            ],
            "domain_regex": [
            ],
            "domain_suffix": [
                ".ru",
                ".su",
                ".by"
            ],
            "geoip": [
                "private",
                "ru",
                "by"
            ],
            "geosite": [
            ],
            "outbound": "direct"
        },
        {
            "outbound": "proxy",
            "process_name": [
                "Discord.exe",
                "chrome.exe"
            ]
        }
    ]
}

```
P.S. Можно прописать свой браузер вместо chrome.exe (он и будет ходить через прокси)

5. Жмякаем OK и еще раз OK
6. Переходим "Настройки" -> "Настройки TUN режима"
![image](https://github.com/user-attachments/assets/d9ddaa02-a0de-4348-80e4-072f1e6f66c3)

7. Прописываем там
```
discord.exe
chrome.exe
```
Вместо `chrome.exe` можно свой браузер

![image](https://github.com/user-attachments/assets/f9f676b0-24f5-4aa9-952a-79107469f123)

8. Жмякаем ок и включаем эти режимы на главном экране

![image](https://github.com/user-attachments/assets/584c4566-9f58-41f8-bd3c-ad9c2d8cac0d)

9. Копируем строку, которую вам скинул и жмякаем по "Сервер" -> "Добавить из буфера обмена"
    
![image](https://github.com/user-attachments/assets/23c8b2c3-211f-478b-8e88-e04124162aee)

10. ПКМ по подключению и жмякаем "Запустить"
    
![image](https://github.com/user-attachments/assets/97881f2f-90c3-4298-b036-39d1aacc618f)

11. Ставим, чтобы программа запускалась всегда сразу
    
![image](https://github.com/user-attachments/assets/84c9d453-2e03-403a-aa75-ebfd8c2fb9c4)



