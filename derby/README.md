Створення простого застосунку на Derby.js

1. Ініціалізація проекту:
Створити нову директорію для проекту:
```Bash
mkdir my-derby-app
cd my-derby-app
```

Ініціалізувати пакет.json:
```Bash
npm init -y
```

2. Установка Derby.js:
```Bash
npm install derby
```

3. Створення основного файлу (app.js):
```JavaScript
const derby = require('derby');
const app = derby.createApp();

// Створення моделі
app.store.define({
  messages: {
    hello: 'Hello, World!'
  }
});

// Створення маршруту
app.get('/', function(req, res) {
  res.render('index', { title: 'My Derby App' });
});

// Запуск сервера
app.listen(3000);
```

4. Створення виду (index.html):
```HTML
<!DOCTYPE html>
<html>
<head>
  <title>{{ title }}</title>
</head>
<body>
  <h1>{{ messages.hello }}</h1>
  <script src="/derby.js"></script>
  <script src="/app.js"></script>
</body>
</html>
```

5. Запуск сервера:
```Bash
node app.js
```

Пояснення коду:
- derby.createApp(): Створює новий екземпляр Derby-додатку.
- app.store.define(): Визначає модель даних. У цьому прикладі ми маємо одну властивість hello зі значенням "Hello, World!".
- app.get('/'): Визначає маршрут для головної сторінки.
- res.render('index', { title: 'My Derby App' }): Рендерить шаблон index.html і передає в нього дані.
- {{ messages.hello }}: Вставляє значення з моделі в шаблон.

Типова структура проекту:
```text
your-derby-app/
├── server
│   ├── models
│   │   └── your_model.js
│   ├── controllers
│   │   └── your_controller.js
│   └── views
│       └── your_view.html
├── client
│   ├── models
│   │   └── your_model.js
│   ├── controllers
│   │   └── your_controller.js
│   ├── views
│       └── your_view.html
├── public
│   └── styles.css
└── package.json
```

Як це працює:
Derby.js автоматично синхронізує дані між сервером і клієнтом. Коли ви запустите сервер і відкриєте в браузері http://localhost:3000, ви побачите повідомлення "Hello, World!".