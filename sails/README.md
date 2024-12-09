Створення простого застосунку на Sails.js

1. Ініціалізація проекту:
Встановіть глобально Sails CLI:
```Bash
npm install -g sails
```

Створіть новий проект:
```Bash
sails new my-sails-app
```

2. Редагування файлу api/controllers/HomeController.js:
```JavaScript
module.exports = {
  index: function (req, res) {
    return res.json({
      message: 'Hello from Sails!'
    });
  }
};
```

3. Запуск сервера:
```Bash
cd my-sails-app
sails lift
```

Пояснення коду:
- api/controllers/HomeController.js: Цей файл містить контролер, який обробляє запити до головної сторінки.
- index: Метод контролера, який відповідає за обробку GET-запитів до кореневого маршруту (/).
- res.json(): Відправляє JSON-відповідь з повідомленням.

Структура проекту:
```text
my-sails-app/
├── api
│   ├── controllers
│   │   └── HomeController.js
│   ├── models
│   └── services
├── assets
├── config
├── node_modules
├── package.json
└── tasks
```

Як це працює:
- api/controllers: Містить логіку контролерів, які обробляють вхідні запити.
- api/models: Визначає моделі даних, які відображають структуру даних у вашій базі даних.
- config: Містить конфігураційні файли для додатку.
- assets: Містить статичні файли, такі як CSS, JavaScript та зображення.