Створення простого застосунку на Express.js
1. Ініціалізація проекту:
Створити нову директорію для проекту:
```Bash
mkdir my-express-app
cd my-express-app
```

Ініціалізувати пакет.json:
```Bash
npm init -y
```

2. Установка Express:
```Bash
npm install express
```

3. Створення основного файлу (app.js):
```JavaScript
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
  res.send('Hello, World!');
});

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`);
});
```

4. Запуск сервера:
```Bash
node app.js
```

Пояснення коду:

- require('express'): Імпортує модуль Express.
- const app = express();: Створює новий екземпляр Express-додатка.
- app.get('/', (req, res) => { ... }): Визначає маршрут для головної сторінки (/). Коли користувач переходить на цю сторінку, функція всередині обробляє запит і відправляє відповідь.
- res.send('Hello, World!');: Відправляє текст "Hello, World!" як відповідь на запит.
- app.listen(port, () => { ... }): Запускає сервер на вказаному порту (за замовчуванням 3000).
- Структура проекту:
my-express-app/
├── package.json
└── app.js

Як це працює:
Коли ви запускаєте node app.js, сервер починає слухати на порту 3000. Коли хтось відкриє браузер і перейде за адресою http://localhost:3000, сервер отримає запит, обробить його відповідно до визначеного маршруту і відправить відповідь "Hello, World!".