Створення простого застосунку на LoopBack

1. Ініціалізація проекту:
Створити нову директорію для проекту:
```Bash
mkdir my-loopback-app
cd my-loopback-app
```

Ініціалізувати пакет.json:
```Bash
npm init -y
```

2. Установка LoopBack:
```Bash
npm install --save @loopback/application-starter
```

3. Створення основного файлу (server.js):
```JavaScript
const loopback = require('@loopback/application');
const { BootMixin } = require('@loopback/boot');

const app = new loopback.Application();
app.boot(BootMixin);

app.get('/', (req, res) => {
  res.send('Hello from LoopBack!');
});

app.start()
  .then(() => {
    console.log('The server is running at http://127.0.0.1:3000');
  })
  .catch(err => {
    console.error('Cannot start the application.', err);
    process.exit(1);
  });
```

4. Запуск сервера:
```Bash
node server.js
```

Пояснення коду:
- const loopback = require('@loopback/application');: Імпортує основний клас для створення додатків LoopBack.
- app.boot(BootMixin);: Ініціалізує базові компоненти додатку.
- app.get('/', (req, res) => { ... }): Визначає маршрут для головної сторінки (/).
- app.start(): Запускає сервер.

Структура проекту:
```text
my-loopback-app/
├── package.json
└── server.js
```

Як це працює:
Коли ви запускаєте node server.js, сервер починає слухати на порту 3000. Коли хтось відкриє браузер і перейде за адресою http://localhost:3000, сервер отримає запит, обробить його відповідно до визначеного маршруту і відправить відповідь "Hello from LoopBack!".

