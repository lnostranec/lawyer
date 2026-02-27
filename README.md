# Lawyer Mail Backend

Небольшой Node.js‑бэкенд для отправки сообщений из формы «Задать вопрос юристу» в Telegram.

## Стек

- Node.js
- Express
- dotenv

## Установка локально

```bash
npm install
npm start
```

Сервер по умолчанию поднимается на порту `3000`.

## Переменные окружения

Настройки берутся из переменных окружения (локально можно использовать файл `.env`, пример — `.env.example`):

```env
TELEGRAM_BOT_TOKEN=your_bot_token_from_BotFather
TELEGRAM_CHAT_ID=your_chat_id
PORT=3000
```

## Эндпоинт

`POST /api/send-question`

Тело запроса в формате JSON:

```json
{
  "name": "Имя пользователя",
  "phone": "+7 900 000-00-00",
  "question": "Текст вопроса юристу"
}
```

Ответ:

```json
{ "success": true }
```

или

```json
{ "success": false, "error": "Описание ошибки" }
```

