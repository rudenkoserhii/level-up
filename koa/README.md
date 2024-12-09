Створення простого застосунку на Koa.js

1. Ініціалізація проекту:
Створити нову директорію для проекту:
```Bash
mkdir my-koa-app
cd my-koa-app
```

Ініціалізувати пакет.json:
```Bash
npm init -y
```

2. Установка Koa.js:
```Bash
npm install koa
```

3. Створення основного файлу (index.js):
```JavaScript
const Koa = require('koa');
const app = new Koa();

app.use(async (ctx) => {
  ctx.body = 'Hello, World!';
});

app.listen(3000);
```

4. Запуск сервера:
```Bash
node index.js
```

Пояснення коду:
- const Koa = require('koa');: Імпортує модуль Koa.
- const app = new Koa();: Створює новий екземпляр Koa-додатка.
- app.use(async (ctx) => { ... }): Визначає middleware, який буде виконуватися для всіх запитів.
- ctx.body = 'Hello, World!';: Встановлює тіло відповіді на "Hello, World!".

Структура проекту:
my-koa-app/
├── package.json
└── index.js

Як це працює:
Коли ви запускаєте node index.js, сервер починає слухати на порту 3000. Коли хтось відкриє браузер і перейде за адресою http://localhost:3000, middleware буде виконаний і відправить відповідь "Hello, World!".