Створення простого застосунку на Hapi.js

1. Ініціалізація проекту:
Створити нову директорію для проекту:
```Bash
mkdir my-hapi-app
cd my-hapi-app
```

Ініціалізувати пакет.json:
```Bash
npm init -y
```

2. Установка Hapi.js:
```Bash
npm install hapi
```

3. Створення основного файлу (index.js):
```JavaScript
const Hapi = require('@hapi/hapi');

const init = async () => {
  const server = Hapi.server({
    port: 3000,
    host: 'localhost'
  });

  server.route({
    method: 'GET',
    path: '/',
    handler: (request, h) => {
      return 'Hello, World!';
    }
  });

  await server.start();
  console.log('Server running on %s', server.info.uri);
};

process.on('unhandledRejection', (err) => {
  console.log(err);
  process.exit(1);
});

init();
```

4. Запуск сервера:
```Bash
node index.js
```

Пояснення коду:
- const Hapi = require('@hapi/hapi');: Імпортує модуль Hapi.
- const server = Hapi.server({ ... }): Створює новий екземпляр сервера Hapi з вказаним портом і хостом.
- server.route({ ... }): Визначає маршрут. Метод GET вказує на те, що це HTTP GET запит.
- handler: (request, h) => { ... }: Це функція обробки запиту. Вона приймає об'єкт запиту request і об'єкт відповіді h.
- return 'Hello, World!';: Повертає рядок як відповідь на запит.

Структура проекту:
```text
my-hapi-app/
├── package.json
└── index.js
```

Як це працює:
Коли ви запускаєте node index.js, сервер починає слухати на порту 3000. Коли хтось відкриє браузер і перейде за адресою http://localhost:3000, сервер отримає запит, обробить його відповідно до визначеного маршруту і відправить відповідь "Hello, World!".