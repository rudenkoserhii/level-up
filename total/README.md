Створення простого застосунку на Total.js

1. Ініціалізація проекту:
Встановіть глобально Total.js CLI:
```Bash
npm install -g total.js
```

Створіть новий проект:
```Bash
total new my-total-app
```

2. Редагування файлу app/controllers/home.js:
```JavaScript
module.exports = {
  index: function (req, res) {
    res.send('Hello from Total.js!');
  }
};
```

3. Запуск сервера:
```Bash
cd my-total-app
total start
```

Пояснення коду:
- app/controllers/home.js: Цей файл містить контролер, який обробляє запити до головної сторінки.
- index: Метод контролера, який відповідає за обробку GET-запитів до кореневого маршруту (/).
- res.send(): Відправляє текстову відповідь.

Структура проекту:
```text
my-total-app/
├── app
│   ├── controllers
│   │   └── home.js
│   ├── models
│   └── views
├── config
├── public
├── routes
└── package.json
```

Як це працює:
- app/controllers: Містить логіку контролерів, які обробляють вхідні запити.
- app/models: Визначає моделі даних, які відображають структуру даних у вашій базі даних.
- app/views: Містить шаблони для рендерингу HTML-сторінок.
- config: Містить конфігураційні файли для додатку.
- public: Містить статичні файли, такі як CSS, JavaScript та зображення.
- routes: Визначає маршрути додатку.