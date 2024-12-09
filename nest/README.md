Створення найпростішого застосунку на Nest.js

1. Ініціалізація проекту:
Встановіть глобально Nest CLI:
```Bash
npm install -g @nestjs/cli
```

Створіть новий проект:
```Bash
nest new my-nest-app
```

2. Редагування файлу src/app.controller.ts:
```TypeScript
import { Controller, Get } from '@nestjs/common';

@Controller()
export class AppController {
  @Get()
  getHello(): string {
    return 'Hello, World!';
  }
}
```

3. Запуск сервера:
```Bash
cd my-nest-app
npm run start
```

Пояснення коду:
- @Controller(): Декоратор, який позначає клас як контролер.
- @Get(): Декоратор, який позначає метод як обробник GET-запитів.
- getHello(): Метод, який повертає рядок "Hello, World!".

Структура проекту:
```text
my-nest-app/
├── package.json
├── src
│   ├── app.controller.spec.ts
│   ├── app.controller.ts
│   ├── app.module.ts
│   ├── app.service.ts
│   └── main.ts
└── test
    ├── app.e2e-spec.ts
```

Як це працює:
- app.controller.ts: містить логіку контролера, який обробляє вхідні запити.
- app.module.ts: головний модуль додатку, де імпортуються всі інші модулі.
- main.ts: точка входу в додаток, яка запускає сервер.
