Створення простого застосунку на Fastify

1. Ініціалізація проекту:
Створити нову директорію для проекту:
```Bash
mkdir my-fastify-app
cd my-fastify-app
```

Ініціалізувати пакет.json:
```Bash
npm init -y
```

2. Установка Fastify:
```Bash
npm install fastify
```

3. Створення основного файлу (index.js):
```JavaScript
const fastify = require('fastify')({ logger: true })

fastify.get('/', async (request, reply) => {
  reply.send('Hello, World!')
})

const start = async () => {
  try {
    await fastify.listen(3000)
    fastify.log.info(`server listening on ${fastify.server.address().port}`)
  } catch (err) {
    fastify.log.error(err)
    process.exit(1)
  }
}

start()
```

4. Запуск сервера:
```Bash
node index.js
```

Пояснення коду:
- const fastify = require('fastify')({ logger: true }): Створює новий екземпляр Fastify з увімкненим логуванням.
- fastify.get('/', async (request, reply) => { ... }): Визначає маршрут для головної сторінки (/). Коли користувач переходить на цю сторінку, функція всередині обробляє запит і відправляє відповідь.
- reply.send('Hello, World!'): Відправляє текст "Hello, World!" як відповідь на запит.
- fastify.listen(3000): Запускає сервер на порту 3000.

Структура проекту:
my-fastify-app/
├── package.json
└── index.js

Як це працює:
Коли ви запускаєте node index.js, сервер починає слухати на порту 3000. Коли хтось відкриє браузер і перейде за адресою http://localhost:3000, сервер отримає запит, обробить його відповідно до визначеного маршруту і відправить відповідь "Hello, World!".

