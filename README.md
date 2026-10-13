# Регистрация участников выставки

Форма регистрации Kosmetik Profi Schulung одним файлом `index.html`: логотипы и база немецких PLZ встроены, зависимостей нет (кроме шрифтов Google Fonts).

## Настройка

В начале скрипта в `index.html` есть блок `CONFIG`:

- `WEBHOOK_URL` — адрес webhook (например, n8n), куда уходит каждая заявка JSON-запросом POST. Пока адрес пустой, форма показывает, что заявка не отправлена.
- `WHATSAPP_CONFIRMATION` — `true`, только если workflow за webhook действительно отправляет подтверждение в WhatsApp.
- `EVENT` — название выставки, уходит вместе с заявкой.

В узле Webhook в n8n нужно указать адрес сайта в «Options → Allowed Origins», иначе браузер заблокирует запрос.

## Поля заявки

`name`, `phone`, `plz`, `city`, `interests`, `interestsText`, `roles`, `rolesText`, `roleOther`, `consentData`, `event`, `source`, `submittedAt`.

## Данные

База индексов: © участники OpenStreetMap, данные на 2021 год.
