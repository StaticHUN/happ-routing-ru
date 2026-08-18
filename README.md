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
  https://raw.githubusercontent.com/runetfreedom/russia-v2ray-rules-dat/release/geosite.dat
  ```
- **GeoIP (IP-адреса)**
  ```plaintext
  https://raw.githubusercontent.com/runetfreedom/russia-v2ray-rules-dat/release/geosite.dat
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
geosite:PRIVATE
geosite:WIN-UPDATE
geosite:WIN-EXTRA
geosite:TLD-RU
geosite:CATEGORY-AI-RU
geosite:CATEGORY-BANK-RU
geosite:CATEGORY-GOV-RU
geosite:CATEGORY-MEDIA-RU
geosite:CATEGORY-RU
geosite:CATEGORY-TRAVEL-RU
geosite:CATEGORY-ECOMMERCE-RU
geosite:MAILRU-GROUP
geosite:NIC-RU
geosite:REGRU
geosite:RU-AVAILABLE-ONLY-INSIDE
geosite:RUTUBE
geosite:APPLE
geosite:APPLE-PKI
geosite:GOOGLE-PLAY
geosite:MICROSOFT
geosite:MICROSOFT-PKI
geosite:HUAWEI
geosite:XIAOMI
geosite:CATEGORY-ANDROID-APP-DOWNLOAD
geosite:F-DROID
geosite:TIKTOK
geosite:TWITCH
geosite:STEAM
geosite:EPICGAMES
geosite:RIOT
geosite:ESCAPEFROMTARKOV
geosite:FACEIT
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
169.254.0.0/16
224.0.0.0/4
255.255.255.255
geoip:PRIVATE
geoip:RU
geoip:RU-WHITELIST
```
</details>

### 🚷 Заблокировать (Block)
Добавьте эти правила, чтобы полностью запретить доступ к нежелательным ресурсам.

<details>
<summary><b>Показать полный список</b></summary>

```plaintext
geosite:CATEGORY-ADS
geosite:WIN-SPY
geosite:CATEGORY-PUBLIC-TRACKER
```
</details>
