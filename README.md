# Shamir Splitter

**Shamir Splitter** — клиентское офлайн-приложение для разделения секретов (seed-фраз, ключей, паролей) на мнемонические доли по стандарту **SLIP-39** (Shamir's Secret Sharing).
[телеграм канал](https://t.me/shamir_splitter)
Приложение представляет собой один HTML-файл без серверной части. Все вычисления выполняются локально в браузере.

---

## Возможности

- **Разделение секрета (Split)** — разбивает seed-фразу, HEX-строку или произвольный текст на N мнемонических долей с настраиваемым порогом восстановления (threshold)
- **Восстановление секрета (Recover)** — собирает исходный секрет из минимально необходимого числа долей
- **BIP-39 совместимость** — автоматически распознаёт 12/15/18/21/24-словные BIP-39 мнемоники и работает напрямую с байтами энтропии
- **QR-коды** — генерация QR-кодов для каждой доли с возможностью скачивания
- **Сканирование QR** — импорт долей через камеру устройства
- **Двуязычный интерфейс** — русский и английский (RU / EN)
- **Самотестирование** — при запуске выполняет roundtrip-тест SLIP-39 split → recover
- **SRI-защита** — целостность CDN-библиотек проверяется через Subresource Integrity хеши
- **Clipboard** — копирование и вставка долей через буфер обмена

## Безопасность

- Весь код выполняется **исключительно на стороне клиента** — данные не покидают браузер
- Приложение можно сохранить и использовать **полностью офлайн**
- CDN-скрипты защищены **SRI-хешами** — подмена на уровне CDN невозможна
- Встроенный **self-test** при загрузке проверяет корректность криптографических операций
- До 16 долей (лимит SLIP-39 спецификации)

## Быстрый старт

1. Скачайте файл `index.html`
2. Откройте его в любом современном браузере
3. Выберите режим **Split** или **Recover**
4. Готово — никакой установки не требуется

Или используйте через GitHub Pages:

```
https://btc-standart.github.io/shamir-splitter/
```

## Технологии

| Компонент | Назначение |
|-----------|------------|
| [SLIP-39](https://github.com/satoshilabs/slips/blob/master/slip-0039.md) | Shamir's Secret Sharing для мнемонических фраз |
| [CryptoJS](https://github.com/brix/crypto-js) | Криптографические примитивы (SHA-256, PBKDF2, AES) |
| [qrcode.js](https://github.com/davidshimjs/qrcodejs) | Генерация QR-кодов |
| [jsQR](https://github.com/cozmo/jsQR) | Чтение QR-кодов с камеры |
| BIP-39 wordlist | Полный английский словарь из 2048 слов |

## Структура проекта

```
shamir-splitter/
├── index.html   ← всё приложение в одном файле
├── LICENSE       ← MIT License
└── README.md
```

## Лицензия

Этот проект распространяется под лицензией [MIT](LICENSE).

---

## Shamir Splitter (English)

**Shamir Splitter** is a client-side offline application for splitting secrets (seed phrases, keys, passwords) into mnemonic shares using the **SLIP-39** standard (Shamir's Secret Sharing).

The entire application is a single HTML file with no server component. All computations happen locally in the browser.

### Features

- **Split** — split a seed phrase, HEX string, or arbitrary text into N mnemonic shares with a configurable recovery threshold
- **Recover** — reconstruct the original secret from the minimum required number of shares
- **BIP-39 compatible** — auto-detects 12/15/18/21/24-word BIP-39 mnemonics and splits raw entropy bytes directly
- **QR codes** — generate downloadable QR codes for each share
- **QR scanning** — import shares via device camera
- **Bilingual UI** — Russian and English (RU / EN)
- **Self-test** — runs a SLIP-39 split → recover roundtrip test on startup
- **SRI protection** — CDN library integrity verified via Subresource Integrity hashes
- **Clipboard** — copy and paste shares

### Quick Start

1. Download `index.html`
2. Open it in any modern browser
3. Choose **Split** or **Recover** mode
4. Done — no installation required

### License

This project is licensed under the [MIT License](LICENSE).
