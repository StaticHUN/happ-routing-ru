[📲 Установить правила маршрутизации Happ](https://statichun.github.io/happ-routing-ru/)

# 🛠️ Настройка маршрутизации для профиля «Default»

В этом руководстве описано, как отредактировать существующий профиль (например, **Default**) в вашем прокси-клиенте (Sing‑box, V2Ray и т.п.) для корректного обхода блокировок и оптимизации трафика.

---

## 1️⃣ Откройте нужный профиль
Перейдите в настройки вашего приложения и выберите профиль **Default** (или тот, который вы используете).

---

## 2️⃣ Обновите Geo‑файлы
Загрузите свежие версии файлов с правилами для геолокаций и сайтов:

- **Geosite (домены)**
  ```plaintext
  https://github.com/StaticHUN/happ-routing-ru/raw/refs/heads/rue/geosite.dat
  ```
- **GeoIP (IP-адреса)**
  ```plaintext
  https://github.com/StaticHUN/happ-routing-ru/raw/refs/heads/rue/geoip.dat
  ```
> 💡 Укажите эти ссылки в настройках геоданных.

---

## 3️⃣ Порядок маршрутизации
В редакторе правил установите приоритет обработки в следующем порядке:

**Block → Direct → Proxy**

Это гарантирует, что блокировки применяются в первую очередь, затем идут прямые подключения, и только потом – через прокси.

---

## 4️⃣ Настройте правила маршрутизации

### 🚫 Прокси (Proxy)
**Оставить пустым** – ничего не добавляйте в этот раздел.

---

### 🔓 Напрямую (Direct)
Добавьте следующие правила – весь этот трафик будет идти в обход прокси, т.е по вашему реальному IP.

<details>
<summary><b>Показать полный список</b></summary>

```plaintext
geosite:private
geosite:win-update
geosite:win-extra
geosite:category-ai-ru
geosite:category-bank-ru
geosite:category-gov-ru
geosite:category-media-ru
geosite:category-ru
geosite:category-travel-ru
geosite:category-ecommerce-ru
geosite:ru-available-only-inside
geosite:rutube
geosite:apple
geosite:apple-pki
geosite:google-play
geosite:microsoft
geosite:microsoft-pki
geosite:huawei
geosite:xiaomi
geosite:category-android-app-download
geosite:f-droid
geosite:faceit
geosite:twitch
geosite:steam
geosite:epicgames
geosite:riot
geosite:escapefromtarkov
geosite:wbgames
geosite:pubg
geosite:origin
geosite:rockstar
geosite:2kgames
geosite:category-game-accelerator-cn
geosite:category-game-platforms-download
geosite:category-games
geosite:category-games-cn
geosite:gamersky
geosite:gamesplanet
geosite:tencent-games
domain:ru
domain:su
domain:рф
77.88.8.8
1.1.1.1
8.8.8.8
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
169.254.0.0/16
224.0.0.0/4
255.255.255.255
geoip:private
geoip:ru
geoip:ru-whitelist
```
</details>

### 🚷 Заблокировать (Block)
Добавьте эти правила, чтобы полностью запретить доступ к нежелательным ресурсам.

<details>
<summary><b>Показать полный список</b></summary>

```plaintext
geosite:category-ads
geosite:win-spy
geosite:category-public-tracker
```
</details>
